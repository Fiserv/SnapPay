# What’s needed for calling any SnapPay API.

The following general instructions apply to every API.

| Name                                 | Value                                                |
|--------------------------------------|------------------------------------------------------|
| Request Type                         | Application/json                                     |
| AccountID                            | SnapPay Account ID                                   |
| UserId                               | API User ID                                          |
| Password                             | API Password                                         |
| Secret Key (API Authentication Code) | Shared Secret Key used for generating HMAC signature |

### Following values are needed for API authentication

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
