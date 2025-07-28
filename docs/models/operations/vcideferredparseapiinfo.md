# VciDeferredParseApiInfo

Information about the credential request bound to the transaction ID.

## Example Usage

```typescript
import { VciDeferredParseApiInfo } from "authelete-bundled/models/operations";

let value: VciDeferredParseApiInfo = {};
```

## Fields

| Field                                                             | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `identifier`                                                      | *string*                                                          | :heavy_minus_sign:                                                | The identifier of the credential offer.                           |
| `format`                                                          | *string*                                                          | :heavy_minus_sign:                                                | The value of the format parameter in the credential request.      |
| `bindingKey`                                                      | *string*                                                          | :heavy_minus_sign:                                                | The binding key specified by the proof in the credential request. |
| `details`                                                         | *string*                                                          | :heavy_minus_sign:                                                | The details about the credential request.                         |