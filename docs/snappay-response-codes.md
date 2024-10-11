# SnapPay Response Codes

This section outlines the response codes you may encounter when interacting with the SnapPay API. The API will return a message description for each response code, providing details on the outcome of an API request.

| Name        | Value                                                                         | Purpose |
|-------------|-------------------------------------------------------------------------------|---------|
|	AM00000001	|	Request is null or empty.	                                                    |	API	|
|	AM00000002	|	Content of request is null or empty.	                                        |	API	|
|	AM00000003	|	Request header is null or empty.	                                            |	API	|
|	AM00000004	|	Account is missing in the header of request.	                                |	API	|
|	AM00000005	|	Authorization or Signature is missing in the header of request.	              |	API	|
|	AM00000006	|	Authentication failed.	                                                      |	API	|
|	AM00000007	|	Account is not active.	                                                      |	API	|
|	AM00000008	|	Account does not exist.	                                                      |	API	|
|	AM00000009	|	Request received.	                                                            |	API	|
|	AM00000010	|	Request in progress.	                                                        |	API	|
|	AM00000011	|	Unable to parse the request.	                                                |	API	|
|	AM00000012	|	Upload completed.	                                                            |	API	|
|	AM00000013	|	Upload failed.	                                                              |	API	|
|	AM00000014	|	Transaction history sent.	                                                    |	API	|
|	AM00000015	|	Unable to validate the request. Please contact your administrator.	          |	API	|
|	AM00000016	|	Request does not exist.	                                                      |	API	|
|	AM00000017	|	Status update sent.	                                                          |	API	|
|	AM00000018	|	Failed to send the status update.	                                            |	API	|
|	AM00000019	|	&1 cannot be null or empty.	                                                  |	API	|
|	AM00000020	|	&1 cannot be more than &2 characters.	                                        |	API	|
|	AM00000021	|	Invalid account.	                                                            |	API	|
|	AM00000022	|	Request from invalid IP address.	                                            |	API	|
|	AM00000023	|	Valid date format YYYY-MM-DD.	                                                |	API	|
|	AM00000024	|	End date must be greater than start date.	                                    |	API	|
|	AM00000032	|	Invalid customer type.	                                                      |	API	|
|	AM00000033	|	Active valid values Y or N.	                                                  |	API	|
|	AM00000034	|	Only letters are valid in &1.	                                                |	API	|
|	AM00000035	|	Allow payment valid values Y or N.	                                          |	API	|
|	AM00000036	|	Invalid account ID in request.	                                              |	API	|
|	AM00000047	|	Invoice Data Upload Status Notification	                                      |	API	|
|	AM00000048	|	Invoice Order Data Upload Status Notification	                                |	API	|
|	AM00000049	|	Customer Data Upload Status Notification	                                    |	API	|
|	AM00000061	|	Billing or shipping valid values B or S.	                                    |	API	|
|	AM00000547	|	Information stored successfully.	                                            |	API	|
|	AM00000548	|	Transaction type not supported.	                                              |	API	|
|	AM00000549	|	Payment method not supported.	                                                |	API	|
|	AM00000550	|	Company and currency setup not found.	                                        |	API	|
|	AM00000581	|	Payment method not supported for transaction type.	                          |	API	|
|	AM00000588	|	Payment methods retrieved successfully.	                                      |	API	|
|	AM00000589	|	Payment methods not found.	                                                  |	API	|
|	AM00000590	|	Active payment methods not found.	                                            |	API	|
|	AM00000602	|	Customer Id not found for account.	                                          |	API	|
|	AM00000603	|	Company and Currency are required.	                                          |	API	|
|	AM00000604	|	Token and amount are required.	                                              |	API	|
|	AM00000605	|	No cards found for transaction.	                                              |	API	|
|	AM00000606	|	Transaction successful.	                                                      |	API	|
|	AM00000607	|	Transaction partially successful.	                                            |	API	|
|	AM00000608	|	Transaction failed.	                                                          |	API	|
|	AM00000609	|	Inactive, deleted or invalid token.	                                          |	API	|
|	AM00000610	|	Merchant information not found.	                                              |	API	|
|	AM00000613	|	Invalid reference transaction ID.	                                            |	API	|
|	AM00000614	|	No transaction found for reference transaction ID.	                          |	API	|
|	AM00000615	|	Invalid transaction amount.	                                                  |	API	|
|	AM00000616	|	User is deleted, inactive or not found for the account.	                      |	API	|
|	AM00000617	|	User ID is required.	                                                        |	API	|
|	AM00000618	|	Invalid amount.	                                                              |	API	|
|	AM00000619	|	Capture cannot be performed for a failed authorization.	                      |	API	|
|	AM00000620	|	Authorization already captured.	                                              |	API	|
|	AM00000621	|	Transaction not found for referencetransactionid.	                            |	API	|
|	AM00000622	|	Cannot perform reference refund for a failed charge.	                        |	API	|
|	AM00000623	|	Charge already refunded.	                                                    |	API	|
|	AM00000624	|	Failed authorizations, charges or payments cannot be voided.	                |	API	|
|	AM00000625	|	Transaction already voided.	|	API	|
|	AM00000626	|	Refund amount cannot exceed charge amount.	|	API	|
|	AM00000666	|	Payment details retrieved successfully.	|	API	|
|	AM00000667	|	No payment details found.	|	API	|
|	AM00000671	|	Invalid pg transaction ID.	|	API	|
|	AM00000672	|	Transaction not found for PG Transaction ID.	|	API	|
|	AM00000681	|	Payment Receipt	|	API	|
|	AM00000683	|	User id, payment method, company and currency are required.	|	API	|
|	AM00000684	|	User id not found for account.	|	API	|
|	AM00000685	|	Payment method not supported.	|	API	|
|	AM00000688	|	No transaction found for the given input.	|	API	|
|	AM00000689	|	Either transactionid, orderid, reference or purchaseorder is required.	|	API	|
|	AM00000690	|	Success	|	API	|
|	AM00000701	|	User is not active.	|	API	|
|	AM00000702	|	Payment Receipt	|	API	|
|	AM00000703	|	Refund Payment Receipt	|	API	|
|	AM00000726	|	Void amount has to be less than actual transaction.	|	API	|
|	AM00000727	|	Invalid void amount.	|	API	|
|	AM00000728	|	Payment method update failed at SnapPay but successful at merchant level.	|	API	|
|	AM00000729	|	Customer name update failed.	|	API	|
|	AM00000730	|	Invalid expiration date.	|	API	|
|	AM00000736	|	Payment method update failed at merchant.	|	API	|
|	AM00000737	|	Type is required for payment method.	|	API	|
|	AM00000738	|	Last 4 is required.	|	API	|
|	AM00000740	|	Transaction requires the following fields when payment method is not found: addressline1, city, state, country, zip, customername, expirationdate, last4, type.	|	API	|
|	AM00000744	|	Customer Payment Method Upload Status Notification	|	API	|
|	AM00000745	|	expirationyear cannot be greater than &1.	|	API	|
|	AM00000746	|	expirationyear should be 4 characters.	|	API	|
|	AM00000747	|	Valid values Y or N or leave blank for enrollautopay.	|	API	|
|	AM00000748	|	Valid values are 01 through 12 for expirationmonth.	|	API	|
|	AM00000749	|	Valid types are VISA, MC, AMEX, DISCOVER, CHECKING, SAVING.	|	API	|
|	AM00000750	|	Invalid expirationyear.	|	API	|
|	AM00000751	|	Invalid last4.	|	API	|
|	AM00000752	|	Tenant is missing in the header of request.	|	API	|
|	AM00000753	|	Invalid tenant.	|	API	|
|	AM00000754	|	No 	|	API	|
|	AM00000785	|	Tokenization is not applicable for configured payment gateway.	|	API	|
|	AM00000786	|	Invalid supplier type.	|	API	|
|	AM00000793	|	Only ACH or debit card supported.	|	API	|
|	AM00000794	|	Supplier Payment Method Upload Status Notification	|	API	|
|	AM00000795	|	Supplier Data Upload Status Notification	|	API	|
|	AM00000796	|	Supplier Invoice Data Upload Status Notification	|	API	|
|	AM00000816	|	Valid types are CHECKING & SAVING.	|	API	|
|	AM00000842	|	Account requires an active supplier. Contact your account administrator.	|	API	|
|	AM00000843	|	Invalid type.	|	API	|
|	AM00000851	|	Enter a valid type of C or S.	|	API	|
|	AM00000859	|	EffectiveFrom date is invalid.	|	API	|
|	AM00000860	|	EffectiveTo date is invalid.	|	API	|
|	AM00000861	|	Deposit information attached.	|	API	|
|	AM00000862	|	No deposit information found.	|	API	|
|	AM00000863	|	Invalid usertypename.	|	API	|
|	AM00000864	|	Invalid usergroupname.	|	API	|
|	AM00000865	|	Invalid usertypename. Valid usertypes are CSR/Customer/CustomerAdmin.	|	API	|
|	AM00000866	|	Invalid usertypename. Valid usertypes are Buyer/Supplier/SupplierAdmin.	|	API	|
|	AM00000867	|	Supplier IDs are either invalid or do not exist.	|	API	|
|	AM00000868	|	Customer IDs are either invalid or do not exist.	|	API	|
|	AM00000869	|	IsActive should be Y or N.	|	API	|
|	AM00000871	|	UserGroup is required.	|	API	|
|	AM00000872	|	User having usertype as Customer or Customer Admin must have customers to associate.	|	API	|
|	AM00000873	|	User having usertype as Supplier or Supplier Admin must have suppliers to associate.	|	API	|
|	AM00000874	|	Welcome email cannot be sent to inactive users.	|	API	|
|	AM00000875	|	Error occurred while sending welcome email.	|	API	|
|	AM00000876	|	Supplier association is not needed for Customer or Customer Admin or CSR type of users.	|	API	|
|	AM00000877	|	Customer association is not needed for Supplier or Supplier Admin or Buyer type of users.	|	API	|
|	AM00000878	|	UserGroup is not compatible with UserType.	|	API	|
|	AM00000879	|	Valid values are Y or N for welcomeemail.	|	API	|
|	AM00000880	|	Customer association is not needed for an user having usertype as &1.	|	API	|
|	AM00000881	|	Supplier association is not needed for an user having usertype as &1.	|	API	|
|	AM00000883	|	User Data Upload Status Notification	|	API	|
|	AM00000884	|	User Data needed for transaction.	|	API	|
|	AM00000885	|	User is an invalid type for transaction.	|	API	|
|	AM00000886	|	User upload failed.	|	API	|
|	AM00000887	|	Authorization(A) only supports credit card when amount is greater than zero.	|	API	|
|	AM00000889	|	Error occurred in &1. Please contact Customer Service.	|	API	|
|	AM00000890	|	Customer upload failed.	|	API	|
|	AM00000891	|	Supplier upload failed.	|	API	|
|	AM00000894	|	User type is required.	|	API	|
|	AM00000895	|	Supplier is required.	|	API	|
|	AM00000896	|	Customer ID is required.	|	API	|
|	AM00000897	|	Supplier ID is required.	|	API	|
|	AM00000899	|	Supplier ID, Company and Currency are required.	|	API	|
|	AM00000910	|	Missing authentication setup.	|	API	|
|	AM00000933	|	AddUserThroughSSO is turned off.	|	API	|
|	AM00000934	|	Validation failed.	|	API	|
|	AM00000935	|	Usertype not supported.	|	API	|
|	AM00000936	|	Usergroup not supported.	|	API	|
|	AM00000961	|	Unsupported document type.	|	API	|
|	AM00000962	|	Error occured when calling the Card Connect API &1.	|	API	|
|	AM00000963	|	Response received from Card Connect.	|	API	|
|	AM00000964	|	Merchant is missing in the header of the request.	|	API	|
|	AM00000965	|	Please Contact SnapPay Administrator to enable CardPointe Integrated Terminal API.	|	API	|
|	AM00000966	|	Merchant setup is missing.	|	API	|
|	AM00000967	|	Device is missing in the header of the request.	|	API	|
|	AM00000968	|	X-CardConnect-SessionKey is missing in the header of the request.	|	API	|
|	AM00000969	|	X-CardConnect-SessionKey is missing in the response header.	|	API	|
|	AM00000972	|	File name should be alpha-numeric and extension should be lower case alpha-numeric.	|	API	|
|	AM00000973	|	Content limit exceeded.	|	API	|
|	AM00000975	|	Invalid status. Status can be S, F or A.	|	API	|
|	AM00001003	|	Lease Numbers are either invalid or do not exist.	|	API	|
|	AM00001008	|	Lease Number is required.	|	API	|
|	AM00001009	|	Lease Version is required.	|	API	|
|	AM00001010	|	Customer ID is required.	|	API	|
|	AM00001011	|	Status is required.	|	API	|
|	AM00001012	|	Status should be A or I.	|	API	|
|	AM00001013	|	Business Unit is required.	|	API	|
|	AM00001014	|	Unit Number is required.	|	API	|
|	AM00001015	|	Invalid Lease Number.	|	API	|
|	AM00001016	|	Effective Date is invalid.	|	API	|
|	AM00001017	|	Ending Date is invalid.	|	API	|
|	AM00001019	|	Invalid Lease Version.	|	API	|
|	AM00001020	|	Payment Receipt for Order &1	|	API	|
|	AM00001021	|	Payment Receipt for Order &1	|	API	|
|	AM00001022	|	Refund Payment Receipt for Order &1	|	API	|
|	AM00001028	|	Error occurred while adding/updating businessunit details.	|	API	|
|	AM00001029	|	Error occurred while adding/updating unit details.	|	API	|
|	AM00001039	|	Customer is not available for given customerid.	|	API	|
|	AM00001040	|	Company is not available for given companycode.	|	API	|
|	AM00001048	|	Lease Data Upload Status Notification	|	API	|
|	AM00001075	|	Invalid status. Status can be I, A or E.	|	API	|
|	AM00001077	|	Invoice lease information is missing.	|	API	|
|	AM00001078	|	Lease updates not allowed for given invoice type.	|	API	|
|	AM00001079	|	ACH payment is turned off for Order.	|	API	|
|	AM00001110	|	Lease Version effective from date is invalid.	|	API	|
|	AM00001111	|	Lease version effective to date is invalid.	|	API	|
|	AM00001141	|	Token is required.	|	API	|
|	AM00001271	|	Customer ID is invalid or Customer ID is missing.	|	API	|
|	AM00001277	|	Invalid checktype.	|	API	|
|	AM00001278	|	Invalid mode.	|	API	|
|	AM00001279	|	Total amount should not be greater than &1. Please contact Customer Service.	|	API	|
|	AM00001281	|	The following column is missing from the upload: &1	|	API	|
|	AM00001287	|	Merchant ID is missing in request.	|	API	|
|	AM00001288	|	Account ID is missing in request.	|	API	|
|	AM00001289	|	Given date format in request is invalid. Format should be yyyymmdd.	|	API	|
|	AM00001290	|	No updates found.	|	API	|
|	AM00001291	|	EnableAccountUpdater is tunerd off for account &1.	|	API	|
|	AM00001292	|	Error occurred while generating response.	|	API	|
|	AM00001295	|	Success.	|	API	|
|	AM00001309	|	Valid request types are C and S.	|	API	|
|	AM00001431	|	Invalid device data	|	API	|
|	AM00001452	|	feeformat for Service fee can be flat or percentage only.	|	API	|
|	AM00001453	|	feeformat for Convenience fee can be flat only.	|	API	|
|	AM00001454	|	waivefee should be Y or N.	|	API	|
|	AM00001460	|	&1 should be of &2 characters.	|	API	|
|	AM00001461	|	Partial refund is not allowed as original transaction has fee.	|	API	|
|	AM00001467	|	&2 valid values &1.	|	API	|
|	AM00001468	|	Invalid 3D secure field entered – secureflag	|	API	|
|	AM00001469	|	Transaction amount is required.	|	API	|
|	AM00001470	|	&1 is invalid.	|	API	|
|	AM00001471	|	Invalid transaction amount.	|	API	|
|	AM00001472	|	Invalid type.	|	API	|
|	AM00001473	|	Invalid email.	|	API	|
|	AM00001475	|	&1 fee will be charged.	|	API	|
|	AM00001476	|	&1 % Service fee will be charged.	|	API	|
|	AM00001477	|	Invalid dlstate.	|	API	|
|	AM00001478	|	Valid identification type is T for Company Check Type.	|	API	|
|	AM00001479	|	Valid identification types are D and S for Personal Check Type.	|	API	|
|	AM00001480	|	dlstate is required for D identification type.	|	API	|
|	AM00001481	|	Fee is waived.	|	API	|
|	AM00001483	|	Invalid 3D secure field entered – secureexemption	|	API	|
|	AM00001491	|	Transaction successful.	|	API	|
|	AM00001495	|	Please wait...	|	API	|
|	AM00001509	|	The payment mode &1 is not applied to this user.	|	API	|
|	AM00001510	|	Payment method &1 is only applicable to User type Customer in SnapPay.	|	API	|
|	AM00001511	|	Payment method &1 is not enabled for an user or usergroup.	|	API	|
|	AM00001512	|	Payment method &1 is only applicable for Transaction type A/S.	|	API	|
|	AM00001513	|	Invalid cardtype.	|	API	|
|	AM00001520	|	&1 is not enabled.	|	API	|
|	AM00001522	|	Customer country must be China for AliPay payments.	|	API	|
|	AM00001529	|	Transaction requires the following fields when payment method is not found: customername.	|	API	|
|	AM00001542	|	Error occurred while processing fee.	|	API	|
|	AM00001543	|	Fee transation failed. Main transaction is voided.	|	API	|
|	AM00001544	|	Transaction is voided.	|	API	|
|	AM00001545	|	iscardpresent should be Y or N.	|	API	|
|	AM00001547	|	Request completed.	|	API	|
|	AM00001548	|	Request failed.	|	API	|
|	AM00001549	|	Transaction Type not supported	|	API	|
|	AM00001553	|	Error in retrieving payment method details for Edit.	|	API	|
|	AM00001554	|	Customer Threshold Upload Status Notification	|	API	|
|	AM00001570	|	Valid txntype is Capture, Credit or Refund.	|	API	|
|	AM00001576	|	IVR feature not available. Please contact administrator.	|	API	|
|	AM00001577	|	Payment method is already associated to token. Please contact administrator.	|	API	|
|	AM00001578	|	Cannot associate payment method more than limit. Please contact administrator.	|	API	|
|	AM00001584	|	Token is missing in request.	|	API	|
|	AM00001585	|	EnableBINAPI feature is turned off for account.	|	API	|
|	AM00001586	|	iscapture valid values Y or N	|	API	|
|	AM00001589	|	This feature is available only for Invoice and Order.	|	API	|
|	AM00001596	|	Retref missing in the request.	|	API	|
|	AM00001597	|	EnableInquireAPI feature is turned off for account.	|	API	|
|	AM00001598	|	Fee feature not available. Please contact administrator.	|	API	|
|	AM00001599	|	Fee amount retrieved successfully.	|	API	|
|	AM00001602	|	Invalid snappay_action	|	API	|
|	AM00001639	|	ACH Rejects found.	|	API	|
|	AM00001640	|	ACH Rejects not found.	|	API	|
|	AM00001654	|	No payment methods found.	|	API	|
|	AM00001656	|	Payment methods found.	|	API	|
|	AM00001657	|	enrolledforautopay should be either Y or N or leave blank then it will defaults to Y.	|	API	|
|	AM00001658	|	Request failed. &1	|	API	|
|	AM00001664	|	customerid is required.	|	API	|
|	AM00001669	|	Paynow url is not configured. Please contact Customer Service.	|	API	|
|	AM00001675	|	EnableSettlementStatus is tunerd off for account &1.	|	API	|
|	AM00001685	|	customerid is required.	|	API	|
|	AM00001686	|	ordernumber is required.	|	API	|
|	AM00001693	|	Order Data Upload Status Notification	|	API	|
|	AM00001700	|	Email is required.	|	API	|
|	AM00001707	|	isactive should be either Y or N or blank.	|	API	|
|	AM00001715	|	No payment methods found for given pagenumber.	|	API	|
|	AM00001716	|	pagenumber should be greater than 0.	|	API	|
|	AM00001719	|	Real Estate module is not enabled for this account.	|	API	|
|	AM00001720	|	No records found.	|	API	|
|	AM00001721	|	Data retrieved successfully.	|	API	|
|	AM00001722	|	Data retrieval failed.	|	API	|
|	AM00001723	|	Invalid process.	|	API	|
|	AM00001724	|	Request failed.	|	API	|
|	AM00001727	|	todate must be greater than fromdate	|	API	|
|	AM00001728	|	fromdate and todate are required fields.	|	API	|
|	AM00001729	|	process is required.	|	API	|
|	AM00001730	|	fromdate or todate format should be YYYY-MM-DD.	|	API	|
|	AM00001731	|	Invalid accountid in request.	|	API	|
|	AM00001735	|	Invalid donotflag. donotflag can be Y or N.	|	API	|
|	AM00001740	|	Capture cannot be performed for an expired authorization.	|	API	|
|	AM00001744	|	Sale transaction was performed due to expired authorization.	|	API	|
|	AM00001745	|	Sale transaction was attempted due to expired authorization.	|	API	|
|	AM00001746	|	Failed to update the Description for Transaction ID &1.	|	API	|
|	AM00001747	|	Transaction Updated Succesfully.	|	API	|
|	AM00001748	|	Transaction successful - amount applied somewhere else.	|	API	|
|	AM00001749	|	Authorization Expired.	|	API	|
|	AM00001750	|	Expired	|	API	|
|	AM00001752	|	Authorization already voided.	|	API	|
|	AM00001763	|	Merchant Properties Upload Status Notification	|	API	|
|	AM00001774	|	Fee may be charged.	|	API	|
|	AM00001778	|	pagenumber should be numeric only.	|	API	|
|	AM00001779	|	Userid is required.	|	API	|
|	AM00001780	|	Firstname is required.	|	API	|
|	AM00001781	|	Lastname is required.	|	API	|
|	AM00001782	|	Usertypename is required.	|	API	|
|	AM00001783	|	Usergroupname is required.	|	API	|
|	AM00001784	|	Invoice having different lease number at line level is not allowed.	|	API	|
|	AM00001789	|	usertypename valid values are accountadmin,buyer,csr,customer,customeradmin,supplier,supplieradmin.	|	API	|
|	AM00001790	|	usergroupname valid values are Customer,CSR,Supplier,Buyer,AccountAdmin.	|	API	|
|	AM00001791	|	isactive valid values are Y or N.	|	API	|
|	AM00001792	|	forcepasswordreset valid values are Y or N.	|	API	|
|	AM00001793	|	forcetermsandconditions valid values are Y or N.	|	API	|
|	AM00001794	|	devicegroup does not exists.	|	API	|
|	AM00001795	|	isdefault valid values are Y or N.	|	API	|
|	AM00001796	|	customerid does not exists.	|	API	|
|	AM00001797	|	associationtype valid values are shipto or soldto.	|	API	|
|	AM00001798	|	Work with shipto is not enabled.	|	API	|
|	AM00001799	|	associationtype is required.	|	API	|
|	AM00001800	|	deleteuser valid values are Y or N.	|	API	|
|	AM00001804	|	User can only be associated to one customer association type.	|	API	|
|	AM00001805	|	Association type &1 is not valid for customer &2.	|	API	|
|	AM00001837	|	Pricing technology feature not available. Please contact administrator.	|	API	|
|	AM00001843	|	Invalid paymentmode. Payment Mode can be CC, ACH or All.	|	API	|
|	AM00001844	|	Invalid requesttype. Request Type can be SendLink, Order or Invoice.	|	API	|
|	AM00001845	|	Invalid transactiontype. Transaction Type can be A, S, D, V, C, R, P, SV, AV or CV.	|	API	|
|	AM00001849	|	Invalid transactiontype. Transaction Type can be &1.	|	API	|
|	AM00001877	|	customername is required.	|	API	|
|	AM00001878	|	addressline1 is required.	|	API	|
|	AM00001879	|	country is required.	|	API	|
|	AM00001880	|	customerid is required.	|	API	|
|	AM00001884	|	Wallet maintenance feature is not available. Please contact the administrator.	|	API	|
|	AM00001886	|	savepaymentmethod and/or saveatcustomer must be ‘Y’	|	API	|
|	AM00001894	|	Customer User Payment Method Upload Status Notification	|	API	|
|	AM00001947	|	Fee configuration not matching.	|	API	|
|	AM00001950	|	Failed	|	API	|
|	AM00001952	|	408 - Timeout	|	API	|
|	AM00001953	|	408	|	API	|
|	AM00001954	|	Timeout	|	API	|
|	AM00001960	|	Please verify multiple payment payload, all merchants should be configured to use UPI	|	API	|
|	AM00001961	|	multiple payment mode is only applicatble fo UPI, please verify merchant configured to use UPI	|	API	|
|	AM00001964	|	Error occurred while reading json file.	|	API	|
|	AM00001965	|	Json file not found to process the request.	|	API	|
|	AM00001966	|	Error occurred while checking for Json in Azure storage location.	|	API	|
|	AM00050001	|	This is for adding disclaimar if any for UPI screen of a SnapPay Account.	|	HPP	|
|	AM00050002	|	Captcha validation failed.	|	HPP	|
|	AM00050003	|	Card Type not supported.	|	HPP	|
|	AM00050004	|	Invalid card number.	|	HPP	|
|	AM00050005	|	Invalid CVV number.	|	HPP	|
|	AM00050006	|	Invalid Phone number.	|	HPP	|
|	AM00050007	|	Invalid expiry month or year.	|	HPP	|
|	AM00050008	|	Cancel UPI Form.	|	HPP	|
|	AM00050009	|	Loading.	|	HPP	|
|	AM00050010	|	Submit UPI Form.	|	HPP	|
|	AM00050011	|	Invalid request.	|	HPP	|
|	AM00050012	|	Page not found.	|	HPP	|
|	AM00050014	|	Payment Page is about to expire in {0} seconds.<br/>Click <B>Stay On Page</B> to continue.	|	HPP	|
|	AM00050015	|	Timed Out	|	HPP	|
|	AM00050016	|	Stay On Page	|	HPP	|
|	AM00050017	|	Cancel	|	HPP	|
|	AM00050018	|	Invalid email.	|	HPP	|
|	AM00050019	|	Unable to complete submission of the transaction. Do not perform transaction again. Contact customer service.	|	HPP	|
|	AM00050020	|	Redirecting. Contact customer service.	|	HPP	|
|	AM00050021	|	Invalid zip code.	|	HPP	|

