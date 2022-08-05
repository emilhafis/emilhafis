---
description: Designed to investigate the status of a QR payment.
---

# QR Investigation Overview

#### UML Diagram

![](<../../.gitbook/assets/UML\_Sequence\_Diagram\_4 (1).png>)

<details>

<summary><strong>Business process</strong></summary>

Third Party App should make investigation requests if not receive <mark style="color:red;">`completed, incompleted, expired, canceled`</mark> response value from [Webhook.](../../api-format/qr-payment-api.md#request-example-3)

1.[**GET /qr-status request**](../../api-format/qr-payment-api.md#request-example-3) **-** Third Party App calls GET method Investigate QR when not receiving answer from QR API Service Provider within specified time frame;

2.**QR investigation -** QR API Service Provider checks QR status;

3.**Sending payment status -** If status (pacs.002/STAT) is received from IPS then QR API Service Provider sends appropriate status to the Third Party;

3.**Sending investigation for QR (pacs.028) -** If status (pacs.002/STAT) is not received from IPS then QR API Service Provider sends investigation (pacs.028) to IPS;

4.**Sending response (pacs.002/STAT) -** IPS sends payment status (pacs.002/STAT) to QR API Service Provider;

5.[**GET /qr-status response**](../../api-format/qr-payment-api.md#response-example-1) **-** QR API Service Provider sends status to the Third party.

</details>
