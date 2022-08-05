---
description: Designed to cancel the generated QR code.
---

# QR Cancel Overview

#### UML Diagram

![](../../.gitbook/assets/UML\_Sequence\_Diagram\_3.png)

<details>

<summary><strong>Business process</strong></summary>

Third party can cancel the active QR code at any time**.**&#x20;

**Initiate purchase -** User initiates purchase by selecting QR payment option form e-com site.

1. **Sending request** [**PUT/qr/{rrn}/cancel**](../../api-format/qr-payment-api.md#cancel-qr) **–** Third Party calls PUT method “Cancel QR” for canceling active QR code;
2. **Sending response** [**PUT/qr/{rrn}/cancel** ](../../api-format/qr-payment-api.md#cancel-qr)**–** QR API Service Providers sends response for PUT method “Cancel QR”.

</details>
