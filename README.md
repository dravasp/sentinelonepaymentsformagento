SentinelOnePayments.com Internet Payment Gateway Module for Magento 2.4x
=====================================================================================

Accessible payments suite through multistep core-banking ecosystem

Install using SSH
```
cd /opt/bitnami/magento
composer require dravasp/sentinelonepaymentsformagento:dev-master
sudo magento-cli setup:upgrade
```

Login to Magento Admin > Configuration > Sales > Payment Methods

Instructions:
==================

[] Request integration form - Ref. to Email with Subject Integration for SentinelOnePayments.com - hello@weskyprint.com - Merchant Onboarding Requisites - `https://sentinelonepayments.com/tnc`
- Complete KYC and Request Approval for Compliance Check
- Compliance Check requires valid About Us, Contact Us, Product Catalogue, Acceptable Terms and Conditions, Privacy Policy and Return, Refund & Cancellation Policy
- Optionally, you may also set Security Policy with Customer Support Method clearly defined > Tollfree Phone / SMS / WhatsApp / Email
- TLS 1.3 with HTTP2.Quic Enabled

[] Changes for going Live.
- Insert your (variables) `MERCHANT IDENTIFIER` + `SALT/ACCESS KEY` + `SECRET KEY` + `TRADE ACCESS CODE` for Production Environment in Stores > Configuration > Sales > Payment Methods > SentinelOnePayments.com Internet Payment Gateway

[] Enabling the module and configuring it with your SentinelOnePayments.com Merchant credentials
- Login to your Magento Admin and go to Store > Configuration.
- On the left side bar, scroll down and click on "Payment Method" under the Sales section.
- Scroll down the page and "Enable" the SentinelOnePayments.com IPG Layer module.
- On the same page, click on "Payment Methods" on the sidebar under the section "SALES".
- On this page, a "SentinelOne CheckoutPaymentGateway" section will appear. Click on it if its not already open.
- Add your `ACCESS KEY` + `SECRET KEY`  here. Also specify sandbox to "NO" Always.
  click "Save Config".
  Additionally, if you want that only buyers from particular country or countries should be able to use SentinelOnePayments.com IPG with Layer Suite enabled,  
  against the "Payment Applicable From" field, select "Specific Countries" and then select the countries in the box
  that opens up. In order to select more than one country, you will need to click on the countries with ctrl key of the
  keyboard pressed. Sort Order field determines in which order SentinelOnePayments.com IPG will be displayed to the buyer during checkout.

[] Testing SentinelOnePayments.com Internet Payment Gateway
- Make sure that sandbox mode is on and all details are entered in the request form submitted for configuration
- Go to your store and place an order.
- If you configured SentinelOnePayments.com IPG Layer correctly in the previous step, it should appear as an option under payment methods during checkout.
- When you click on checkout, it should redirect you to `SUCCESS` order.

[] Checking the status of payment transaction at SentinelOnePayments.com Internet Payment Gateway from your Magento Admin
- Login to admin and under Sales, click on Orders
- Click on the first order in the data grid. This should be the order that you just placed
- When the order details page opens up, look for "Payment Information" block.
  Inside the block, you can see the latest status of the transaction.

You will now be able to integrate SentinelOnePayments.com Internet Payment Gateway with your existing Merchant Services Account of choice where you host your Merchant Account

Merchant Account or Cash Collection Service Account with Innovative ```Banking Partners``` allows high order value or high frequency volume (recurring trxns.)

Benefits of Merchant Services as opposed to standard Integration -
```
Get an integrated, rules-based, proactive risk management system that is supported by industry standard security
Enjoy 99.9% uptime and a 24-hour helpdesk support
Get customised MIS solutions for your business needs
```

You can apply for a Merchant Account with IDFC Bank or Kotak Mahindra Bank / SBM Bank (India) / Bank of Baroda / HDFC Bank / ICICI Bank / YES Bank (Any One) for unprecedented scale

```
Account Reconciliation / Revenue Insights + Affordable Pricing for Growth - Scale
````

[] Corporate Office Address  - India's Accelerated Payment Gateway
```
  - WE SKY PRINT LLP - Mumbai, MH, India (Remote)
```	
	Opens : 2 PM to 6 PM Everyday - 4 PM to 6 PM IST Saturday  Closed : 2nd & 4th Saturday and every Sunday
  
  - Technical Documentation Usage - `https://github.com/dravasp/sentinelonepaymentsformagento/blob/main/README.md`
  
  - Customer Care at `innovate@sentinelonepayments.com` (Mon-Fri 10am to 6pm IST) / Raise a Ticket via `Web Chat` or Designated Account Manager
  
[] Important Emails for Corporate Communications and Risk Assessment
	- Corporate Communications - Risk Alert - https://sentinelonepayments/responsible-disclosure-policy / Vuln. Report `security@sentinelonepayments.com`
	
[] Install using `composer require dravasp/sentinelonepaymentsformagento:dev-master`
  - Please Do Not Run composer with sudo or install in project root directory / Please Do Not Upload Static Files to Webserver.
  - Request Integration Support or Seek Guidance from Repo Maintainers
   
```
- BASE_URL_UAT - Offline Payments
- BASE_URL_SANDBOX - Offline Payments
- const ALLOWED_CURRENCIES = ['INR']
```
	Check Trxn. Details via Bitnami Magento 2.4x Admin Order Dashboard `Login` - `Sales > Orders > Select Latest Order` > Transaction ID with Details - `CAPTURE`

  - Support and Documentation - Forum - `https://sentinelonepayments.com`

  - For Testing UAT run 
		md5 <filename>

  - Example
	```
	md5 /opt/bitnami/magento/var/log/system.log
	```
	inside SSH Terminal to provide verification to VAS Team
	
  - One-page Checkout Enabled for Magento Commerce OS - Bitnami
  
  Uninstall
```	
	sudo magento-cli module:disable SentinelOne_CheckoutPaymentGateway
	composer remove dravasp/sentinelonepaymentsformagento
	sudo magento-cli setup:upgrade
	sudo magento-cli module:status
```	

  Hard Delete an Plugin / Extension
```
	sudo nano /bitnami/magento/app/etc/config.php
	Page Down to SentinelOne_CheckoutPaymentGateway
	Delete and make sure there are no trailing spaces
	CTRL/CMD + X and Click Y to Save without Renaming the file
```
```	composer dump-autoload
	sudo magento-cli setup:upgrade
```
```	Wait for a few minutes RUN command
	sudo /opt/bitnami/ctlscript.sh restart
	Wait for a few minutes and Re-check
```

New Registration for Merchants - Press Kit - Unveiling Soon

Subscribe to `MATRIX Communications WAP Service` for `Terminal` Access even in Remote Locations.
- Register your interest at https://matrix.in
- Complete KYC with TRAI Required

As per payment gateway policies and liability shift clause, it is merchant responsibility to adhere to PCI Compliant CMS through Payment Acceptance Directives

View Patch Type - `Required` or `Optional` (in the Display Patch Grid by following commands below)
The great part about using Bitnami Magento OS is they are all updated where mandatory security patches are applied to each release. You can view all patches applicable to your specific installation - `https://devdocs.magento.com/quality-patches/tool.html#patch-grid`

Steps to Follow - Login to SSH > cd to Magento Directory
`cd /opt/bitnami/magento`

```
sudo magento-cli maintenance:enable
composer require magento/quality-patches
./vendor/bin/magento-patches status
```
```
Select '2' Adobe Commerce Support followed by '1' to Display All Available Requred and Optional Patches
./vendor/bin/magento-patches apply MDVA-30106 MDVA-12304
```

```
Steps to Revert via Single Command -
./vendor/bin/magento-patches revert MDVA-30106 MDVA-12304
```

| Magento 2.4x on Bitnami  | Optional/REQUIRED  |  Patch Prefix
| ------------- | ------------- | ------------- |
| MDVA-30106 | Optional  |  MDVA
| MDVA-12304 | Optional  |  MDVA
| MDVA-19640 | Optional  |  MDVA
| MDVA-41061-V4 | Optional  |  MDVA
| MDVA-38346 | Optional  |  MDVA
| MDVA-38626 | Optional  |  MDVA
| MDVA-38728 | Optional  |  MDVA
| MDVA-41305-V2 | Optional  |  MDVA
| MDVA-42790 | Optional  |  MDVA
| MDVA-42269 | Optional  |  MDVA
| MDVA-42237 | Optional  |  MDVA
| MDVA-42410 | Optional  |  MDVA
| MDVA-41136 | Optional  |  MDVA
| MDVA-41628 | Optional  |  MDVA
| MDVA-42950 | Optional  |  MDVA
| MDVA-42689 | Optional  |  MDVA
| MDVA-41229 | Optional  |  MDVA
| MDVA-39605 | Optional  |  MDVA
| MDVA-43862 | Optional  |  MDVA
| MDVA-43824 | Optional  |  MDVA
| MDVA-43491 | Optional  |  MDVA
| MDVA-43601 | Optional  |  MDVA
| MDVA-44188 | Optional  |  MDVA
| MDVA-42283 | Optional  |  MDVA
| MDVA-43983 | Optional  |  MDVA
| MDVA-44100 | Optional  |  MDVA
| MDVA-43605 | Optional  |  MDVA
| MDVA-43102 | Optional  |  MDVA
| MDVA-43178 | Optional  |  MDVA
| MDVA-44887 | Optional  |  MDVA
| MDVA-44660 | Optional  |  MDVA
| MDVA-44703 | Optional  |  MDVA
| MDVA-44940 | Optional  |  MDVA
| MDVA-44562 | Optional  |  MDVA
| MDVA-43167 | Optional  |  MDVA
| MDVA-42807 | Optional  |  MDVA

```
Select '2' Adobe Commerce Support followed by '1' to Display All Available Requred and Optional Patches
./vendor/bin/magento-patches apply ACSD-45143 ACSD-44591
```

```
Steps to Revert via Single Command -
./vendor/bin/magento-patches revert ACSD-45143 ACSD-44591
```


| Magento 2.4x on Bitnami  | Optional/REQUIRED  |  Patch Prefix
| ------------- | ------------- | ------------- |
| ACSD-45143 | Optional  |  ACSD
| ACSD-44591 | Optional  |  ACSD
| ACSD-45169 | Optional  |  ACSD
| ACSD-45424 | Optional  |  ACSD
| ACSD-46146 | Optional  |  ACSD
| ACSD-45255 | Optional  |  ACSD
| ACSD-45488 | Optional  |  ACSD
| ACSD-45754 | Optional  |  ACSD
| ACSD-46213 | Optional  |  ACSD
| ACSD-46192 | Optional  |  ACSD
| ACSD-46404 | Optional  |  ACSD
| ACSD-46703 | Optional  |  ACSD
| ACSD-44851 | Optional  |  ACSD
| ACSD-45675 | Optional  |  ACSD
| ACSD-46869 | Optional  |  ACSD

```
sudo magento-cli cache:clean
sudo magento-cli indexer:reindex
sudo magento-cli maintenance:disable
```

You can avoid indexer:reindex command by entering
```
sudo magento-cli setup:upgrade
```
