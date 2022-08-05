---
description: >-
  Multibank Payment Platform provides real time dynamic and static QR codes to
  third party sites for receiving payments.
---

# Overview

![](.gitbook/assets/q.png)

**What is QR payment platform?**

Platform designed for third party sites (e.g. e-commerce, terminal) to get static and dynamic QR codes based customer payment information.&#x20;

**How to use?**

* Firstly you should register your merchant via [Merchant Onboarding API](api-format/merchant-onboarding-api.md) or our Dashboard (coming soon);
* If needed you can update Merchant info via [Merchant Details Modification API](api-format/merchant-onboarding-api.md#merchant-details-modification);
* Get QR code image (base64) or string by sending payment details using [Generate QR API](api-format/qr-payment-api.md#generate-qr);
* Track statuses for each step of the payment process via [<mark style="color:blue;">Status QR via Webhook</mark>](api-format/qr-payment-api.md#status-qr-via-webhook);
* If needed cancel the generated QR code at the customer's request via[ Cancel QR API](api-format/qr-payment-api.md#cancel-qr);
* Investigate status of payment at any time via [Investigate QR API](api-format/qr-payment-api.md#investigate-qr);
* Get a report about QR payments via [QR Report API](api-format/qr-report.md);
* If needed get our [demo QR](https://dev.multibank.az/).
