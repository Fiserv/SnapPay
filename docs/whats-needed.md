# What’s needed for calling any SnapPay API

The following general instructions apply to every API.

| Name                                 | Value                                                |
|--------------------------------------|------------------------------------------------------|
| Request Type                         | Application/json                                     |
| AccountID                            | SnapPay Account ID                                   |
| UserId                               | API User ID                                          |
| Password                             | API Password                                         |
| Secret Key (API Authentication Code) | Shared Secret Key used for generating HMAC signature |

## Following values are needed for API authentication

1.  API user ID
2.  API password
3.  HMAC Signature using shared secret key (add a key “Signature” in request header with HMAC value generated using content of the request and shared secret key)



## List of APIs  
  
### iFrame related APIs

[Get Request ID](../api/?type=post&path=/api/interop/GetRequestID)  
[Get Payment Details](../api/?type=post&path=/api/interop/GetPaymentDetails)

### Non UI APIs

[Tokenize](../api/?type=post&path=/api/interop/Tokenize)  
[Authorize](../api/?type=post&path=/api/interop/Authorize)  
[Charge](../api/?type=post&path=/api/interop/Charge)  
[Capture](../api/?type=post&path=/api/interop/Capture)  
[Credit](../api/?type=post&path=/api/interop/Credit)  
[Refund](../api/?type=post&path=/api/interop/Refund)  
[Void](../api/?type=post&path=/api/interop/Void)  
[Transaction History](../api/?type=post&path=/api/interop/TransactionHistory)  
[Funding History](../api/?type=post&path=/api/interop/FundingHistory)  
[Bin Info](../api/?type=post&path=/api/interop/binapi)  

### Card Account Updater APIs

[Get Updater](../api/?type=post&path=/AccountUpdater/GetUpdater)  
[Put Updater](../api/?type=post&path=/AccountUpdater/PutUpdater)  
[Delete Updater](../api/?type=post&path=/AccountUpdater/DeleteUpdater)  

### HMAC Generation Logic

Following information is needed to generate HMAC signature that will be added to the header variable. 

1. API Authentication Code (wYNLEzZFE4+e9FAk5Rvifnn7hWwFgBGYcHA9+v2Y4dg=)
  
2. SnapPay API URL - https://restapi-stage.snappayglobal.com/api/XXXXXXX where XXXXXXX refers to actual method name that you are calling
  
3. HTTP Method GET or POST 
  
4. SnapPay Account ID 10 digit Account ID (**1000000001**) 
Content in bold text are sample values for documentation purpose, please check with your account manager to get your account specific values.

### Steps to Create HMAC signature


**_1.	Create Request Time Stamp in UTC (GMT) this is to make sure that the incoming request is within certain time limit._**

DateTime epochStart = new DateTime(1970, 01, 01, 0, 0, 0, 0, DateTimeKind.Utc); TimeSpan timeSpan = DateTime.UtcNow - epochStart; 
string requestTimeStamp = Convert.ToUInt64(timeSpan.TotalSeconds).ToString();

**_2.	Create a unique identifier (mostly GUID) for each request._**

string nonce = Guid.NewGuid().ToString("N");

**_3.	Check if the request contains body, usually will be null with HTTP GET requests. Leave this step if the request is GET._**

if (req.Content != null) 
{ 
requestContentBase64String = req.Content. ReadAsStringAsync ().Result; 
}

**_4.	Create the raw signature string in the given format._**

signatureRawData = accountid + requestHttpMethod + requestUri + requestTimeStamp + nonce + requestContentBase64String

**_5.	Convert API Authentication Code to base 64 string._**

var secretKeyByteArray = Convert.FromBase64String(apiAuthCode);

**_6.	Convert raw signature data to UTF 8 encoded byte array._**

byte[] signature = Encoding.UTF8.GetBytes(signatureRawData);

**_7.	Create HMAC signature from API Authentication Code which is converted to base 64 string._**

string requestSignatureBase64String = string.Empty; 
using (HMACSHA256 hmac = new HMACSHA256(secretKeyByteArray)) 
{ 
//convert encoded utf-8 signature to hash 
byte[] signatureBytes = hmac.ComputeHash(signature); 
//convert hash signature to base 64 string 
requestSignatureBase64String = Convert.ToBase64String(signatureBytes); 
}


**_8.	Get base 64 encoded string._**

string HmacValue = Convert.ToBase64String(string.Format("{0}:{1}:{2}:{3}", accountid, requestSignatureBase64String, nonce, requestTimeStamp))

**_9.	Add the HMAC to request header._**

req.Headers.Authorization = new AuthenticationHeaderValue("Hmac ", HmacValue);


### HMAC Example
Hmac MTAwMDAyOTQyNTpdftgzRFROWi96elMyeS9xSnpDRG1nT3ZzRldzakdGWlVjVHBjRkhIeGo4PTo0ODJhMzBiNzZkZDQ0MTM4YjUzODE0NDEyNDE1NmFmMToxNzI0NDEyODEza

### Sample Code
DateTime epochStart = new DateTime(1970, 01, 01, 0, 0, 0, 0, DateTimeKind.Utc);
TimeSpan timeSpan = DateTime.UtcNow - epochStart;
string requestTimeStamp = Convert.ToUInt64(timeSpan.TotalSeconds).ToString();
string nonce = Guid.NewGuid().ToString("N");
requestContentBase64String = req.Content.ReadAsStringAsync().Result;
signatureRawData = accountid + requestHttpMethod + requestUri + requestTimeStamp + nonce + requestContentBase64String;
var secretKeyByteArray = Convert.FromBase64String(apiAuthCode);
byte[] signature = Encoding.UTF8.GetBytes(signatureRawData);
string requestSignatureBase64String = string.Empty;
HMACSHA256 hmac = new HMACSHA256(secretKeyByteArray);
byte[] signatureBytes = hmac.ComputeHash(signature);
string requestSignatureBase64String = Convert.ToBase64String(signatureBytes);
string HmacValue = Convert.ToBase64String(string.Format("{0}:{1}:{2}:{3}", accountid, requestSignatureBase64String, nonce, requestTimeStamp));

### Adding Request Header 
req.Headers.Authorization = new AuthenticationHeaderValue("Hmac ", HmacValue);

