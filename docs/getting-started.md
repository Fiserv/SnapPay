# Getting Started

This document provides details for any external application to integrate with SnapPay for credit card and ACH transactions in a PCI compliant way. Common use cases include:

- Accepting credit cards on eCommerce sites and authorizing payment prior to completing the order, then capturing the funds after the goods or services have been supplied.

- Accepting credit cards directly in an internal or customer facing system

- Accepting bank payments (ACH) directly in an internal or customer facing system

The first set of API’s support use cases that involve user interaction through an iFrame based user interface. These support presenting a list of cards saved on file, adding a new card using a PCI secure method and either performing an authorization, a sale (also referred to as an Auth and Capture) or just returning the token for the ACH or CC account for later use.

The second set of API’s do not involve a user interface but require a CC or ACH token to perform an authorization, capture funds related to an authorization, charge a sale (authorization and capture in a single call), request a credit, request a refund or void a prior transaction. CC or ACH tokens to use with these APIs are created using the first set of user interface APIs that allow a user to enter a credit card or bank account.
