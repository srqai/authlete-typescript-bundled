# JoseVerifyApiFormResponse

## Example Usage

```typescript
import { JoseVerifyApiFormResponse } from "authelete-bundled/models/operations";

let value: JoseVerifyApiFormResponse = {};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `resultCode`                                               | *string*                                                   | :heavy_minus_sign:                                         | The code which represents the result of the API call.      |
| `resultMessage`                                            | *string*                                                   | :heavy_minus_sign:                                         | A short message which explains the result of the API call. |
| `valid`                                                    | *boolean*                                                  | :heavy_minus_sign:                                         | The result of the verification on the JOSE object.<br/>    |
| `signatureValid`                                           | *boolean*                                                  | :heavy_minus_sign:                                         | The result of the signature verification.<br/>             |
| `missingClaims`                                            | *string*[]                                                 | :heavy_minus_sign:                                         | The list of missing claims.<br/>                           |
| `invalidClaims`                                            | *string*[]                                                 | :heavy_minus_sign:                                         | The list of invalid claims.<br/>                           |
| `errorDescriptions`                                        | *string*[]                                                 | :heavy_minus_sign:                                         | The list of error messages.<br/>                           |