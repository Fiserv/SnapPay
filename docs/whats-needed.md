# What’s needed for calling any SnapPay API.

The following general instructions apply to every API.

Name

Value

End Point URLs  
  
These are production URLs. Test URLs will be provided during test account setup.

## iFrame related APIs

[Get Request ID](../api/?type=post&path=/api/Interop/GetRequestID)
[Get Payment Details](../api/?type=post&path=/api/Interop/GetPaymentDetails)

## Non UI APIs

[https://restapi.snappayglobal.com/api/Interop/Tokenize](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/Interop/Tokenize__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykmE5oRf2$)  
[https://restapi.snappayglobal.com/api/Interop/Authorize](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/Interop/Authorize__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykhmgF_E9$)  
[https://restapi.snappayglobal.com/api/Interop/Charge](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/Interop/Charge__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_yktFnrwWl$)  
[https://restapi.snappayglobal.com/api/Interop/Capture](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/Interop/Capture__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykorJURwz$)  
[https://restapi.snappayglobal.com/api/Interop/Credit](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/Interop/Credit__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_yksQ39NwV$)  
[https://restapi.snappayglobal.com/api/Interop/Refund](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/Interop/Refund__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykl3FRPsZ$)  
[https://restapi.snappayglobal.com/api/Interop/Void](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/Interop/Void__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykj_Tc6KW$)  
[https://restapi.snappayglobal.com/api/TransactionHistory](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/TransactionHistory__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykgJIicej$)  
[https://restapi.snappayglobal.com/api/FundingHistory](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/FundingHistory__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykuj3fz_a$)  
[https://restapi.snappayglobal.com/api/bin](https://urldefense.com/v3/__https://restapi.snappayglobal.com/api/bin__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykvfbWExX$)  

## CAU APIs

[https://restapi.snappayglobal.com/AccountUpdater/GetUpdater](https://urldefense.com/v3/__https://restapi.snappayglobal.com/AccountUpdater/GetUpdater__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_yko4_QO44$)  
[https://restapi.snappayglobal.com/AccountUpdater/PutUpdater](https://urldefense.com/v3/__https://restapi.snappayglobal.com/AccountUpdater/PutUpdater__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykmWuribJ$)  
[https://restapi.snappayglobal.com/AccountUpdater/DeleteUpdater](https://urldefense.com/v3/__https://restapi.snappayglobal.com/AccountUpdater/DeleteUpdater__;!!P9vvK-4S!1K3DQo-5wOnM3FyywnbnB68mmIlM7ZXdiA_elnRr4boFLQhPYuDU3WjNE1_ykq_fdGBb$)

Request Type

Application/json

AccountID

SnapPay Account ID

Authentication

### Following values are needed for API authentication

1.  API user ID
2.  API password
3.  HMAC Signature using shared secret key (add a key “Signature” in request header with HMAC value generated using content of the request and shared secret key)

UserId

API User ID

Password

API Password

Secret Key (API Authentication Code)

Shared Secret Key used for generating HMAC signature.
