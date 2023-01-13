# Rejection motives

|  Code |               ISO Name               |                                                                Definition                                                               |
| :---: | :----------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------: |
|       |                                      |                                                                                                                                         |
|  AC01 |      InvalidDebtorAccountNumber      |                                              Debtor account number is invalid or missing.                                               |
|  AC03 |     InvalidCreditorAccountNumber     |                                                Creditor account number invalid or missing                                               |
|  AC04 |       ClosedDebtorAccountNumber      |                              Debtor account number specified has been closed on the bank of account's books                             |
|  AC05 |      ClosedCreditorAccountNumber     |                             Creditor account number specified has been closed on the bank of account's books                            |
|  AC06 |         BlockedDebtorAccount         |                           Debtor account specified is blocked, prohibiting posting of transactions against it.                          |
|  AC07 |        BlockedCreditorAccount        |                          Creditor account specified is blocked, prohibiting posting of transactions against it.                         |
|  AC08 |     InvalidDebtorAccountCurrency     |                                              Debtor account currency is invalid or missing                                              |
|  AC09 |    InvalidCreditorAccountCurrency    |                                             Creditor account currency is invalid or missing                                             |
|  AC10 |         ExpiredDebtorAccount         |                                                        Debtor account is expired                                                        |
|  AC14 |        ExpiredCreditorAccount        |                                                       Creditor account is expired                                                       |
|  AC02 |             DifferAccount            |                                             Creditor account doesn’t belong to this terminal                                            |
|  AC11 |           ExpiredDebtorCard          |                                                 Card linked to Debtor account is expired                                                |
|  AC15 |          ExpiredCreditorCard         |                                                Card linked to Creditor account is expired                                               |
|  AC12 |           BlockedDebtorCard          |                                      Account is blocked by Debitor agent or Card Processing Center                                      |
|  AC16 |          BlockedCreditorCard         |                                      Account is blocked by Creditor agent or Card Processing Center                                     |
|  AC13 |           ClosedDebtorCard           |                                       Account is closed by Debitor agent or Card Processing Center                                      |
|  AC17 |          ClosedCreditorCard          |                                      Account is closed by Creditor agent or Card Processing Center                                      |
|  AC18 |          NotActiveDebtorCard         |                                                        Debtor Card is not Active                                                        |
|  AC19 |         NotActiveCreditorCard        |                                                       Creditor Card is not Active                                                       |
|  AM02 |           NotAllowedAmount           |                                   Specific transaction/message amount is greater than allowed maximum                                   |
|  AM03 |             DifferAmount             |                                        Amount is differ than provided on the stage of initiation                                        |
|  AM04 |           InsufficientFunds          |                               Amount of funds available to cover specified message amount is insufficient.                              |
|  AM05 |              Duplication             |                                                               Duplication                                                               |
|  AM12 |             InvalidAmount            |                                                       Amount is invalid or missing                                                      |
|  AG01 |     TransactionForbiddenbyDebtor     |                             Transaction forbidden on this type of account by Debtor (formerly No Agreement)                             |
|  AG02 |    TransactionForbiddenbyCreditor    |                            Transaction forbidden on this type of account by Creditor (formerly No Agreement)                            |
|  AG03 |    TransactionNotSupportedbyDebtor   |                                   Transaction type not supported/authorized by Debtor on this account                                   |
|  AG05 |   TransactionNotSupportedbyCreditor  |                                  Transaction type not supported/authorized by Creditor on this account                                  |
|  AG04 |    NotPermittedTransactionbyDebtor   |                                                Transaction not permitted by Debtor agent                                                |
|  AG06 |   NotPermittedTransactionbyCreditor  |                                               Transaction not permitted by Creditor agent                                               |
|  AG07 | NotPermittedTransactionthroughAniPay |                                                 Transaction not permitted through AniPay                                                |
|  AG09 |        OriginalPaymentMissing        |                                                   Original payment was never received.                                                  |
|  AG10 |     NotPermittedTransactionbyCPC     |                                              Transaction not permitted by processing center                                             |
|  ARDT |      AlreadyReturnedTransaction      |                                                      Already returned original SCT                                                      |
|  CUST |          RejectedByCustomer          |                                                     Request rejected by the Customer                                                    |
|  CEXP |            ExpiredConsent            |                                                            Consent is expired                                                           |
|  DT01 |          DeclinedTransaction         |                                                     Transaction was already returned                                                    |
|  DT02 |           SecurityViolation          |                                                Transaction declined by Security violation                                               |
|  DT03 |             LawViolation             |                                                 Transaction declined by Violation of law                                                |
|  DF01 |        FeeUnacceptablebyDebtor       |                                                    Unacceptable fee (by Debtor agent)                                                   |
|  DF02 |       FeeUnacceptablebyCreditor      |                                                   Unacceptable fee (by Creditor agent)                                                  |
|  FR01 |             FraudDetected            |                                                         Fraud activity detected.                                                        |
| MERCH |          CancelledByMerchant         |                                                     Request rejected by the Merchant                                                    |
|  MS02 |      NotSpecifiedReasonCustomer      |                                              Reason has not been specified by end customer                                              |
|  MS03 |        NotSpecifiedReasonAgent       |                                                 Reason has not been specified by agent.                                                 |
|  NOAS |         NoAnswerFromCustomer         |                                                        No response from customer                                                        |
|  RR01 | MissingDebtorAccountOrIdentification | Specification of the debtor’s account or unique identification needed for reasons of regulatory requirements is insufficient or missing |
|  RR02 |      MissingDebtorNameOrAddress      |             Specification of the debtor’s name and/or address needed for regulatory requirements is insufficient or missing.            |
|  IM01 |            InvalidMerchant           |                                                   Invalid merchant (by Debitor agent)                                                   |
|  RA01 |            ContactAcquirer           |                                                      Contact acquirer (by Acquirer)                                                     |
|  RO02 |          ReferedOrganisation         |                                              Refer to your organisation (by Debitor agent)                                              |
|  AU01 |         AuthenticationFailed         |                                             Payer autentification failed (by Debitor agent)                                             |
|  AU02 |          AuthenticationNone          |                                             Customer method doesnt exist (by Debitor agent)                                             |
|  AU03 |       SCAAuthenticationRequired      |                                                         Authentication Required                                                         |
|  WD01 |        DebtorExceedAmountLimit       |                                                   Debtor customer exceeds amount limit                                                  |
|  WD02 |      DebtorExceedFrequencyLimit      |                                                 Debtor customer exceeds frequency limit                                                 |
|  WC01 |       CreditorExceedAmountLimit      |                                                  Creditor customer exceeds amount limit                                                 |
|  WC02 |     CreditorExceedFrequencyLimit     |                                                Creditor customer exceeds frequency limit                                                |
|  TN01 |              InvalidTın              |                                                       TIN is invalid or missing.                                                        |
|  BLCD |          InvalidBudgetLevel          |                                    Code of budget level (for Treasury payments) is invalid or missing                                   |
|  BCCD |      InvalidBudgetClassification     |                               Code of budget classification (for Treasury payments) is invalid or missing                               |
|  TECH |           TechnicalProblem           |                        Cancellation requested following technical problems resulting in an erroneous transaction                        |
| QREXP |               ExpiredQR              |                                                       Generated QR code is expired                                                      |
| QRCNL |          CancelledQRPayment          |                                                         QR payment is cancelled                                                         |
| QRCMP |          CompletedQRPayment          |                                                       QR payment already completed                                                      |
