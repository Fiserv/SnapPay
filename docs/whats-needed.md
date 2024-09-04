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
  
2. SnapPay API URL - https://[siteurl]/api/interop/[apiname]
   
4. HTTP Method GET or POST 
  
5. SnapPay Account ID 10 digit Account ID (**1000000001**) 
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

**_1. C# Code_**
<br>
HttpRequestMessage req = new HttpRequestMessage("GET", "apiurl");<br>
req.Content = new StringContent(inputJSONstring, Encoding.UTF8, "application/json");<br>
DateTime epochStart = new DateTime(1970, 01, 01, 0, 0, 0, 0, DateTimeKind.Utc); <br>
TimeSpan timeSpan = DateTime.UtcNow - epochStart;<br>
string requestTimeStamp = Convert.ToUInt64(timeSpan.TotalSeconds).ToString();<br>
string nonce = Guid.NewGuid().ToString("N");<br>
if (includeBody.Equals("Yes"))<br>
{<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
if (req.Content != null)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
{<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
if (useMd5.Equals("Yes"))<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
{<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
byte[] content = req.Content.ReadAsByteArrayAsync().Result;<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
MD5 md5 = MD5.Create();<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
byte[] requestContentHash = null;<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
if (content.Length != 0)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
{<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
requestContentHash = md5.ComputeHash(content);<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
}<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
if (requestContentHash != null)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
{<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
requestContentBase64String = Convert.ToBase64String(requestContentHash);<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
}<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
}<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
else<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
{<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
requestContentBase64String = req.Content.ReadAsStringAsync().Result;<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
}<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
}<br>
}<br>
signatureRawData = accountid + requestHttpMethod + requestUri + requestTimeStamp + nonce + requestContentBase64String;<br>
var secretKeyByteArray = Convert.FromBase64String(apiAuthCode);<br>
byte[] signature = Encoding.UTF8.GetBytes(signatureRawData);<br>
string requestSignatureBase64String = string.Empty;<br>
HMACSHA256 hmac = new HMACSHA256(secretKeyByteArray);<br>
byte[] signatureBytes = hmac.ComputeHash(signature);<br>
string requestSignatureBase64String = Convert.ToBase64String(signatureBytes);<br>
string signatureData = string.Format("{0}:{1}:{2}:{3}", accountid, requestSignatureBase64String, nonce, requestTimeStamp);<br>
string hmacValue = "Hmac " + Convert.ToBase64String(Encoding.UTF8.GetBytes(signatureData));<br>

**_2. JAVA Code_**
<br>String hmacValue = "";
<br>String requestUri = pUrl;
<br>String requestContentBase64String = "";
<br>String requestTimeStamp = Long.toString(TimeUnit.MILLISECONDS.toSeconds(System.currentTimeMillis()));
<br>
<br>UUID uuid = UUID.randomUUID();
<br>String nonce = uuid.toString();
<br>
<br>if (!pMethod.equalsIgnoreCase("GET"))
<br>{
<br>    &nbsp;&nbsp;&nbsp;byte[] payload = payLoad.getBytes(StandardCharsets.UTF_8);
<br>    &nbsp;&nbsp;&nbsp;MessageDigest md = MessageDigest.getInstance("MD5");
<br>    &nbsp;&nbsp;&nbsp;md.update(payload);
<br>    &nbsp;&nbsp;&nbsp;requestContentBase64String = new String(DatatypeConverter.printBase64Binary(md.digest()));
<br>}
<br>String signatureRawData = pAccount + pMethod + requestUri + requestTimeStamp + nonce + requestContentBase64String;
<br>byte[] secretKeyByteArray = DatatypeConverter.parseBase64Binary(pKey);
<br>byte[] signature;
<br>signature = signatureRawData.getBytes("UTF-8");
<br>String requestSignatureBase64String = "";
<br>Mac sha256_HMAC = Mac.getInstance("HmacSHA256");
<br>SecretKeySpec secret_key = new SecretKeySpec(secretKeyByteArray, "HmacSHA256");
<br>sha256_HMAC.init(secret_key);
<br>byte[] Signaturebytes = sha256_HMAC.doFinal(signature);
<br>requestSignatureBase64String = new String(DatatypeConverter.printBase64Binary(Signaturebytes));
<br>String hmacData = pAccount + ":" + requestSignatureBase64String + ":" + nonce + ":" + requestTimeStamp;
<br>hmacValue = new String(DatatypeConverter.printBase64Binary(hmacData.getBytes()));
<br>
<br>
**_3. JAVAScript Code_**
<br>var apiAuthCode = [apiauthcode];
<br>var accountid = [accountid];
<br>var url = [siteurl]/api/interop/[apiname];
<br>var requestHttpMethod = POST or GET
<br>var txttimestamp = "";
<br>var epochStart = new Date(Date.UTC(1970, 01, 01, 0, 0, 0, 0));
<br>var timeSpan = Date.now() - epochStart;
<br>txttimestamp = timeSpan;
<br>var txtnonce = createGuid();
<br>const obj = 
<br>{
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  "accountid": [accountid],
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  "orderid": [orderid]
<br>};
<br>const myJSON = JSON.stringify(obj);
<br>let bytesContent = CryptoJS.enc.Utf8.parse(myJSON);
<br>var md = CryptoJS.MD5(bytesContent);
<br>var mdresult = md.toString(CryptoJS.enc.Base64);
<br>var signatureRawData = accountid + requestHttpMethod + url + txttimestamp +txtnonce;
<br>var secretkey = CryptoJS.enc.Base64.parse(apiAuthCode);
<br>var prehash = CryptoJS.enc.Utf8.parse(signatureRawData);
<br>var hash = generateHash(prehash,secretkey);
<br>var signature = hash.toString(CryptoJS.enc.Base64);
<br>var signatureData = accountid + ":" + signature + ":" + txtnonce + ":" + txttimestamp;
<br>var prehash1 = CryptoJS.enc.Utf8.parse(signatureData);
<br>var HmacValue = prehash1.toString(CryptoJS.enc.Base64);
<br>function generateHash(prehash,secretkey)
<br>{
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;	var hashText = CryptoJS.HmacSHA256(prehash,secretkey);
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;	return hashText ;
<br>}
<br>function createGuid()
<br>{
<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return 'xxxxxxxxxxxx4xxxyxxxxxxxxxxxxxxx'.replace(/[xy]/g, function(c) {
<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var r = Math.random()*16|0, v = c === 'x' ? r : (r&0x3|0x8);
<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return v.toString(16);
<br> });
<br>}
<br>function unpack(str) 
<br>{
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   var bytes = [];
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   for (var i = 0; i < str.length; i++) 
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      var char = str.charCodeAt(i);
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      bytes.push(char >>> 8);
 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     bytes.push(char & 0xFF);
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   }
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   return bytes;
<br>}


