---
description: Designed to generate QR based on payment information.
---

# QR Generation Overview

#### UML Diagram



![](<../../.gitbook/assets/UML\_Sequence\_Diagram (3) (1).png>)

<details>

<summary><strong>Business process</strong></summary>

1. **Initiate purchase -** User initiates purchase by selecting QR payment option form e-com site;
2. **Selecting QR payment option -** User select payment via QR;
3. ****[**POST /qr-generate request** ](../../api-format/qr-payment-api.md#generate-qr)**-** Third Party Site calls POST method “Generate QR” request for receiving QR string or image;
4. **QR generation -** QR API Service Provider generates QR string or image;
5. ****[**POST /qr-generate response**](../../api-format/qr-payment-api.md#response-example) **-** QR API Service Provider response to Third Party Site according to ‘Generate QR response’’ method;
6. **Displaying QR for scan -** Third party site displays QR for scanning by **** user**.**

</details>
