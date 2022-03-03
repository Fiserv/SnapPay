APIs without User Interaction
=============================

API - Get Payment Details
-------------------------

The GetPaymentDetails API returns the results of the GetRequestID and iFrame interaction to allow for further business processing like completing the order creation process on an eCommerce site after successful card authorization. This API also returns a list of all failed transactions.

API – Tokenize
--------------

The Tokenize API provides a token back when credit card is sent in clear text. This API also tokenizes ACH (bank account) details. The token ID is returned on success and can be used in subsequent calls like Authorize, Charge, etc.

API – Authorize
---------------

The Authorize API performs a credit card authorization request using a credit card token to insure the credit card is valid and has the requested credit limit available. The authorization code is returned on success and error information if not successful. The Capture API will then need to be called to actually request the funds transfer.

API – Capture
-------------

The Capture API performs the capture of a prior authorization returned by the Authorize API using a credit card token to initiate the transfer of funds.

API – Charge
------------

The Charge API performs a credit card charge or payment using a credit card token to insure the credit card is valid, has the requested credit limit available and to initiate the transfer of funds. This performs the functions of the Authorize API and Capture API in a single call.

API – Credit
------------

The Credit API places a credit on the credit card or ACH account

API – Refund
------------

The Refund API places a refund of a prior Capture or Charge on the credit card or ACH account used in the original transaction. The original transaction is set in parameter referencetransactionid and some explanatory text can be set in the reference parameter.

API – Void
----------

The Void API attempts to void or cancel a prior authorization transaction. The original authorization transaction is set in parameter referencetransactionid and some explanatory text can be set in the reference parameter. For voding charge and capture transaction, use refund API.

API – GetTransaction
--------------------

The GetTransaction API allows to inquire on a previous transaction. This API allows to inquire on a previous transaction based on transaction ID, order ID, reference or purchase order. The response contains a list of transactions as more than one transaction can have same order ID, reference or purchase order.

API - Transaction History Download
----------------------------------

The TransactionHistory download API can report all payment transactions that have occurred on the SnapPay portal. Based on account configuration, this can include payments on the EIPP portal, as well as through the interoperability API’s. Payment information includes invoice details for a complete picture of the intended accounting of the payment.  
New payments since the last time the API was called are returned by default. This allows calling the API multiple times during the day and being assured that only transactions you have not already received will be returned. If a date range is provided, all transactions within that range will be reported each time the API is called. Note that the date range is passed as header input in the url.  
For credit card payments, only funded transactions can be reported based on account configuration. This provides a simplified interface to an accounting system, but delays transaction reporting until funding information is available (usually a few days).

API - Funding History Download
------------------------------

This API reports amounts that are funded in merchant bank account along with payment transactions. Payment transactions include credit card transactions. ACH transactions are considered funded if SnapPay does not receive any reject for five business days.  
This API is supported for CardConnect and CardX only.

API – Bin Information
---------------------

The bin API allows you to use a CardConnect CardSecure token to determine what type of payment card is being used. The first six (6) digits of a credit card are known as the Bank Identifier Number (BIN), also known as an Issuer Identification Number (IIN).  
This API is application only for CardConnect payment gateway.
