# Error Motives

| Error                                                              | HTTP Status   | Description                                                                      |
| ------------------------------------------------------------------ | ------------- | -------------------------------------------------------------------------------- |
| <mark style="color:red;">INVALID\_TERMINAL\_TYPE</mark>            | BAD\_REQUEST  | The terminal type {type} is " + "invalid. See api docs for possible values       |
| <mark style="color:red;">INVALID\_ALIAS\_TYPE</mark>               | BAD\_REQUEST  | The alias type {type} is invalid. " + "See api docs for possible values          |
| <mark style="color:red;">NULL\_ALIAS\_DETAILS</mark>               | BAD\_REQUEST  | Alias details are null or missing                                                |
| <mark style="color:red;">NULL\_ALIAS\_VALUE</mark>                 | BAD\_REQUEST  | Alias value is null                                                              |
| <mark style="color:red;">NULL\_TERMINAL\_NUMBER</mark>             | BAD\_REQUEST  | Terminal number is null                                                          |
| <mark style="color:red;">INVALID\_ENTITY\_NAME</mark>              | BAD\_REQUEST  | Entity name {name} is invalid                                                    |
| <mark style="color:red;">INVALID\_BRANCH\_NAME</mark>              | BAD\_REQUEST  | Branch name {name} is invalid                                                    |
| <mark style="color:red;">QR\_NOT\_FOUND</mark>                     | BAD\_REQUEST  | QrCode not found with given rrn {rrn}                                            |
| <mark style="color:red;">INVALID\_HEX\_LENGTH</mark>               | SERVER\_ERROR | The calculated hex {hex}, length {length} is invalid                             |
| <mark style="color:red;">MERCHANT\_NOT\_FOUND\_WITH\_ID</mark>     | NOT\_FOUND    | Merchant with the id {id} not found                                              |
| <mark style="color:red;">BRANCH\_NOT\_FOUND\_WITH\_ID</mark>       | NOT\_FOUND    | Branch with the id {id} not found                                                |
| <mark style="color:red;">MERCHANT\_NOT\_FOUND\_WITH\_KEY</mark>    | BAD\_REQUEST  | Merchant not found for the api key                                               |
| <mark style="color:red;">TERMINAL\_NOT\_FOUND\_ADD\_ONE</mark>     | NOT\_FOUND    | No terminal found, please add one                                                |
| <mark style="color:red;">NO\_TERMINAL\_FOUND\_FOR\_MERCHANT</mark> | NOT\_FOUND    | No terminal with terminal number {number} found for merchant with id {id}        |
| <mark style="color:red;">TERMINAL\_ALREADY\_EXISTS</mark>          | BAD\_REQUEST  | Terminal with terminal number {number} already exists for merchant id {merchant} |
