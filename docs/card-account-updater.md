# Card Account Updater APIs

The Card Account Updater (CAU) service provides merchants the ability to keep their customers' card data up-to-date. The Card Account Updater API includessupport pagination of GET requests, and the ability to submit DELETE requests.

*   Use the PutUpdater method to manually submit tokens to the Card Account Updater service.
*   Use the GetUpdater method to retrieve data about recent updates.
*   Use the DeleteUpdater method to manually remove tokens from the Card Account Updater service.

Notes:

1.  Card Account Updater is only available for merchants on the First Data North and Rapid Connect back-end processors.
2.  This service only provides updates for Visa, Mastercard, and Discover accounts.

# API – PutUpdater

The PutUpdater request enrolls accounts in the Card Account Updater service manually, by supplying tokens. These accounts are monitored for changes in account status, expiry, or card number. Card Account Updater relies on information provided by Visa, Mastercard, and Discover to determine when a change has occurred, and stores the changes for retrieval using the GET method.

# API – DeleteUpdater

The DELETE request unenrolls accounts that have been manually added using the PUT method.

# API – GetUpdater

The GET request retrieves all available account changes that have occurred within the 30 day period preceding the current date, or within the previous number of days specified using the daysBack parameter.
