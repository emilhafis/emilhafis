# IPS status process by MSolution

## Overview

After receiving pain.001 message format from MSolution:

1. IPS processes pain.001 and send pain.002 status to MSolution
2. MSolution process pain.002 status [as described diagram below](ips-status-process-by-msolution.md#pain.002-processing-by-msolution)

{% hint style="info" %}
Timeout is 5 minutes in IPS for pain.001 processing.&#x20;

So IPS must receive answer from each bank within 5 minutes.&#x20;

If IPS not receives response from Debtor bank (Taxi Park's bank) within 5 minutes then sends pain.002 STAT to MSolution with rejection motive:

**`EP252`**` `` ```&#x20;

**`Query rejected by timeout`**` ```&#x20;

If IPS not receives response from Creditor bank (Driver's bank) within 5 minutes then sends pain.002 STAT to MSolution with rejection motive::

**`EL202`**`  ``` &#x20;

**`NRT - Rejected by timeout`**
{% endhint %}

## Pain.002 processing by MSolution

<figure><img src=".gitbook/assets/diagram(1) (1).svg" alt=""><figcaption></figcaption></figure>
