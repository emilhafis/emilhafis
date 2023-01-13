# IPS status process by MSolution

After receiving pain.001 message format from MSolution

1. IPS processes pain.001 and send pain.002 status to MSolution
2. MSolution process pain.002 status as described diagram below

{% hint style="info" %}
Timeout for pain.001 processing within IPS is 5 minutes.&#x20;

So IPS must receive answer from banks within 5 minutes.&#x20;

If not receives answer from banks then IPS sends pain.002 STAT to MSolution with Timeout rejection motives:&#x20;

`EP252 Query rejected by timeout` - Timeout from Debtor bank (Taxi Park's bank)

`EL202 NRT - Rejected by timeout` - Timeot from Creditor bank (Driver's bank)
{% endhint %}

<figure><img src=".gitbook/assets/diagram(1) (1).svg" alt=""><figcaption></figcaption></figure>
