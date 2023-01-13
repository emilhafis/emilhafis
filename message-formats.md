# Message formats

## Pain.002&#x20;

{% hint style="info" %}
Pain.002 is a status message for pain.001. IPS sends pain.002 after processing pain.001 receiving from MSolution&#x20;
{% endhint %}

### Pain.002 examples

<details>

<summary>pain.002 success </summary>

```xml
<Document xmlns="urn:iso:std:iso:20022:tech:xsd:pain.002.001.10">  
  <CstmrPmtStsRpt> 
    <GrpHdr> 
      <MsgId>Q9373362/p92</MsgId>  
      <CreDtTm>2023-01-13T10:37:51.003</CreDtTm>  
      <InitgPty> 
        <Id> 
          <OrgId> 
            <AnyBIC>NABZAZ2CIPS</AnyBIC> 
          </OrgId> 
        </Id> 
      </InitgPty>  
      <FwdgAgt> 
        <FinInstnId> 
          <BICFI>NABZAZ2CMEP</BICFI> 
        </FinInstnId> 
      </FwdgAgt> 
    </GrpHdr>  
    <OrgnlGrpInfAndSts> 
      <OrgnlMsgId>NABZAZ2CAMEP230113138130000259785</OrgnlMsgId>  
      <OrgnlMsgNmId>pain.001.001.09</OrgnlMsgNmId>  
      <OrgnlCreDtTm>2023-01-13T10:37:42</OrgnlCreDtTm>  
      <GrpSts>ACSP</GrpSts> 
    </OrgnlGrpInfAndSts>  
    <OrgnlPmtInfAndSts> 
      <OrgnlPmtInfId>NABZAZ2CAMEP230113138130000259785</OrgnlPmtInfId>  
      <TxInfAndSts> 
        <OrgnlInstrId>PAYMFROMMERCHANT</OrgnlInstrId>  
        <OrgnlEndToEndId>PAYM0001</OrgnlEndToEndId>  
        <TxSts>ACSP</TxSts>  
        <OrgnlTxRef> 
          <IntrBkSttlmAmt Ccy="AZN">0.46</IntrBkSttlmAmt>  
          <ReqdExctnDt> 
            <Dt>2023-01-13</Dt> 
          </ReqdExctnDt>  
          <PmtTpInf> 
            <LclInstrm> 
              <Prtry>CPRQ</Prtry> 
            </LclInstrm> 
          </PmtTpInf>  
          <PmtMtd>TRF</PmtMtd>  
          <RmtInf> 
            <Strd> 
              <RfrdDocInf> 
                <Tp> 
                  <CdOrPrtry> 
                    <Prtry>MSID</Prtry> 
                  </CdOrPrtry> 
                </Tp>  
                <Nb>IBAZAZ2XAXXX230113382650000492173</Nb> 
              </RfrdDocInf> 
            </Strd> 
          </RmtInf> 
        </OrgnlTxRef> 
      </TxInfAndSts> 
    </OrgnlPmtInfAndSts> 
  </CstmrPmtStsRpt> 
</Document>
```



</details>

<details>

<summary>pain.002 unsucces - AM04 </summary>

This message generated when insufficient balance in Debtor customer (Taxi Park)

```xml
<Document xmlns="urn:iso:std:iso:20022:tech:xsd:pain.002.001.10">  
  <CstmrPmtStsRpt> 
    <GrpHdr> 
      <MsgId>Q9352652/p92</MsgId>  
      <CreDtTm>2023-01-10T14:48:07.381</CreDtTm>  
      <InitgPty> 
        <Id> 
          <OrgId> 
            <AnyBIC>NABZAZ2CIPS</AnyBIC> 
          </OrgId> 
        </Id> 
      </InitgPty>  
      <FwdgAgt> 
        <FinInstnId> 
          <BICFI>NABZAZ2CMEP</BICFI> 
        </FinInstnId> 
      </FwdgAgt> 
    </GrpHdr>  
    <OrgnlGrpInfAndSts> 
      <OrgnlMsgId>NABZAZ2CAMEP230110705050000258015</OrgnlMsgId>  
      <OrgnlMsgNmId>pain.001.001.09</OrgnlMsgNmId>  
      <OrgnlCreDtTm>2023-01-10T14:48:03</OrgnlCreDtTm>  
      <GrpSts>RJCT</GrpSts> 
    </OrgnlGrpInfAndSts>  
    <OrgnlPmtInfAndSts> 
      <OrgnlPmtInfId>NABZAZ2CAMEP230110705050000258015</OrgnlPmtInfId>  
      <TxInfAndSts> 
        <OrgnlInstrId>PAYMFROMMERCHANT</OrgnlInstrId>  
        <OrgnlEndToEndId>PAYM0001</OrgnlEndToEndId>  
        <TxSts>RJCT</TxSts>  
        <StsRsnInf> 
          <Rsn> 
            <Prtry>EA178</Prtry> 
          </Rsn>  
          <AddtlInf>RTP was rejected by authorizer</AddtlInf> 
        </StsRsnInf>  
        <StsRsnInf> 
          <Rsn> 
            <Prtry>AM04</Prtry> 
          </Rsn>  
          <AddtlInf>Insufficient funds</AddtlInf> 
        </StsRsnInf>  
        <OrgnlTxRef> 
          <IntrBkSttlmAmt Ccy="AZN">8.00</IntrBkSttlmAmt>  
          <ReqdExctnDt> 
            <Dt>2023-01-10</Dt> 
          </ReqdExctnDt>  
          <PmtTpInf> 
            <LclInstrm> 
              <Prtry>CPRQ</Prtry> 
            </LclInstrm> 
          </PmtTpInf>  
          <PmtMtd>TRF</PmtMtd> 
        </OrgnlTxRef> 
      </TxInfAndSts> 
    </OrgnlPmtInfAndSts> 
  </CstmrPmtStsRpt> 
</Document>
```

</details>

<details>

<summary>pain.002 unsuccess - EL202</summary>

This message generated when Creditor bank (Taxi Park Bank) does not respond message received from IPS within 5 minutes

```xml
<Document xmlns="urn:iso:std:iso:20022:tech:xsd:pain.002.001.10">  
  <CstmrPmtStsRpt> 
    <GrpHdr> 
      <MsgId>Q9337292/p92</MsgId>  
      <CreDtTm>2023-01-08T02:08:14.919</CreDtTm>  
      <InitgPty> 
        <Id> 
          <OrgId> 
            <AnyBIC>NABZAZ2CIPS</AnyBIC> 
          </OrgId> 
        </Id> 
      </InitgPty>  
      <FwdgAgt> 
        <FinInstnId> 
          <BICFI>NABZAZ2CMEP</BICFI> 
        </FinInstnId> 
      </FwdgAgt> 
    </GrpHdr>  
    <OrgnlGrpInfAndSts> 
      <OrgnlMsgId>NABZAZ2CAMEP230108747030000256456</OrgnlMsgId>  
      <OrgnlMsgNmId>pain.001.001.09</OrgnlMsgNmId>  
      <OrgnlCreDtTm>2023-01-08T02:07:53</OrgnlCreDtTm>  
      <GrpSts>RJCT</GrpSts> 
    </OrgnlGrpInfAndSts>  
    <OrgnlPmtInfAndSts> 
      <OrgnlPmtInfId>NABZAZ2CAMEP230108747030000256456</OrgnlPmtInfId>  
      <TxInfAndSts> 
        <OrgnlInstrId>PAYMFROMMERCHANT</OrgnlInstrId>  
        <OrgnlEndToEndId>PAYM0001</OrgnlEndToEndId>  
        <TxSts>RJCT</TxSts>  
        <StsRsnInf> 
          <Rsn> 
            <Prtry>EL202</Prtry> 
          </Rsn>  
          <AddtlInf>NRT - Rejected by timeout</AddtlInf> 
        </StsRsnInf>  
        <OrgnlTxRef> 
          <IntrBkSttlmAmt Ccy="AZN">150.00</IntrBkSttlmAmt>  
          <ReqdExctnDt> 
            <Dt>2023-01-08</Dt> 
          </ReqdExctnDt>  
          <PmtTpInf> 
            <LclInstrm> 
              <Prtry>CPRQ</Prtry> 
            </LclInstrm> 
          </PmtTpInf>  
          <PmtMtd>TRF</PmtMtd> 
        </OrgnlTxRef> 
      </TxInfAndSts> 
    </OrgnlPmtInfAndSts> 
  </CstmrPmtStsRpt> 
</Document>
```



</details>

<details>

<summary>pain.002 unsuccess - EP252</summary>

This message generated when Debtor bank (driver's bank) does not respond message received from IPS within 5 minutes

```xml
<Document xmlns="urn:iso:std:iso:20022:tech:xsd:pain.002.001.10">  
  <CstmrPmtStsRpt> 
    <GrpHdr> 
      <MsgId>Q9337319/p92</MsgId>  
      <CreDtTm>2023-01-08T03:12:06.693</CreDtTm>  
      <InitgPty> 
        <Id> 
          <OrgId> 
            <AnyBIC>NABZAZ2CIPS</AnyBIC> 
          </OrgId> 
        </Id> 
      </InitgPty>  
      <FwdgAgt> 
        <FinInstnId> 
          <BICFI>NABZAZ2CMEP</BICFI> 
        </FinInstnId> 
      </FwdgAgt> 
    </GrpHdr>  
    <OrgnlGrpInfAndSts> 
      <OrgnlMsgId>NABZAZ2CAMEP230108939550000256461</OrgnlMsgId>  
      <OrgnlMsgNmId>pain.001.001.09</OrgnlMsgNmId>  
      <OrgnlCreDtTm>2023-01-08T03:11:46</OrgnlCreDtTm>  
      <GrpSts>RJCT</GrpSts> 
    </OrgnlGrpInfAndSts>  
    <OrgnlPmtInfAndSts> 
      <OrgnlPmtInfId>NABZAZ2CAMEP230108939550000256461</OrgnlPmtInfId>  
      <TxInfAndSts> 
        <OrgnlInstrId>PAYMFROMMERCHANT</OrgnlInstrId>  
        <OrgnlEndToEndId>PAYM0001</OrgnlEndToEndId>  
        <TxSts>RJCT</TxSts>  
        <StsRsnInf> 
          <Rsn> 
            <Prtry>EP252</Prtry> 
          </Rsn>  
          <AddtlInf>Query rejected by timeout</AddtlInf> 
        </StsRsnInf>  
        <OrgnlTxRef> 
          <IntrBkSttlmAmt Ccy="AZN">20.00</IntrBkSttlmAmt>  
          <ReqdExctnDt> 
            <Dt>2023-01-08</Dt> 
          </ReqdExctnDt>  
          <PmtTpInf> 
            <LclInstrm> 
              <Prtry>CPRQ</Prtry> 
            </LclInstrm> 
          </PmtTpInf>  
          <PmtMtd>TRF</PmtMtd> 
        </OrgnlTxRef> 
      </TxInfAndSts> 
    </OrgnlPmtInfAndSts> 
  </CstmrPmtStsRpt> 
</Document>
```

</details>

