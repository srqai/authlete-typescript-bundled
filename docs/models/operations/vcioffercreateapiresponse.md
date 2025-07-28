# VciOfferCreateApiResponse

## Example Usage

```typescript
import { VciOfferCreateApiResponse } from "authelete-bundled/models/operations";

let value: VciOfferCreateApiResponse = {};
```

## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `resultCode`                                                                             | *string*                                                                                 | :heavy_minus_sign:                                                                       | The code which represents the result of the API call.                                    |
| `resultMessage`                                                                          | *string*                                                                                 | :heavy_minus_sign:                                                                       | A short message which explains the result of the API call.                               |
| `action`                                                                                 | [operations.VciOfferCreateApiAction](../../models/operations/vcioffercreateapiaction.md) | :heavy_minus_sign:                                                                       | The result of the `/vci/offer/create` API call.                                          |
| `info`                                                                                   | [operations.VciOfferCreateApiInfo](../../models/operations/vcioffercreateapiinfo.md)     | :heavy_minus_sign:                                                                       | N/A                                                                                      |