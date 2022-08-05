---
description: Designed to inform Third Party Sites about processing status.
---

# QR Webhook Status Overview

#### UML Diagram

![](../../.gitbook/assets/UML\_Sequence\_Diagram\_2.png)

<details>

<summary><strong>Business process</strong></summary>

**Initiate purchase -** User initiates purchase by selecting QR payment option form e-com site.

1. **Sending OBIS Read Status –** When users scan QR code read status is sent to QR API Service Provider thru Central Bank;
2. **Sending status PUT/qr{rrn}/status -** QR API Service Provider calls PUT method “QR Processing status” for sending read status to Third Party for information;
3. **Sending OBIS Paid Status –** When users confirm QR payment paid status is sent to QR API Service Provider thru Central Bank;
4. **Sending status PUT/qr{rrn}/status -** QR API Service Provider calls PUT method “QR Processing status” for sending paid status to Third Party for information;
5. **Sending OBIS Cancel Status –** When users cancel QR payment cancel status is sent to QR API Service Provider thru Central Bank;
6. **Sending status PUT/qr{rrn}/status -** QR API Service Provider calls PUT method “QR Processing status” for sending cancel status to Third Party for information;
7. **Sending payment status (pacs.002/STAT) –** When payment completed Central Bank sends payment status (pacs.002/STAT) to QR API Service Provider;
8. **Sending status PUT/qr{rrn}/status -** QR API Service Provider calls PUT method “QR Processing status” for sending payment status to Third Party.

</details>

{% hint style="info" %}
Recommended actions for Third Party when receiving status:

* **Receiving **<mark style="color:red;">**read**</mark>** status** - When receives <mark style="color:red;">read</mark> status, display notification -  “QR code oxuduldu. Zəhmət olmasa ödənişi təsdiqləyin”
* **Receiving **<mark style="color:red;">**paid**</mark>** status** - Display notification - “Ödənişi təsdiq etdiniz. Zəhmət olmasa gözləyin”
* **Receiving **<mark style="color:red;">**canceled**</mark>** status**  - “Ödənişdən imtina etdiniz”
* **Receiving **<mark style="color:red;">**expired**</mark>** status** - “QR code üzrə təyin olunmuş vaxt başa çatmışdır. Zəhmət olmasa yenidən cəhd edin”
* **Receiving **<mark style="color:red;">**incompleted**</mark>** status** - “Əməliyyatınız “xxx - qayıdan description” səbəbdən uğursuz olmuşdur. Zəhmət olmasa yenidən cəhd edin”
* **Receiving **<mark style="color:red;">**completed**</mark>** status** - “Əməliyyatınız uğurla başa çatmışdır”

Note: <mark style="color:red;">read, paid, canceled</mark> is an informational status. If this status is not received then wait <mark style="color:red;">expired, incompleted</mark> or <mark style="color:red;">completed</mark>, not end transaction.
{% endhint %}
