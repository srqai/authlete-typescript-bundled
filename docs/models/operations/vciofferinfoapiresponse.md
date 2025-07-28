# VciOfferInfoApiResponse

## Example Usage

```typescript
import { VciOfferInfoApiResponse } from "authelete-bundled/models/operations";

let value: VciOfferInfoApiResponse = {};
```

## Fields

| Field                                                                                | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `resultCode`                                                                         | *string*                                                                             | :heavy_minus_sign:                                                                   | The code which represents the result of the API call.                                |
| `resultMessage`                                                                      | *string*                                                                             | :heavy_minus_sign:                                                                   | A short message which explains the result of the API call.                           |
| `action`                                                                             | [operations.VciOfferInfoApiAction](../../models/operations/vciofferinfoapiaction.md) | :heavy_minus_sign:                                                                   | The result of the `/vci/offer/info` API call.                                        |
| `info`                                                                               | [operations.VciOfferInfoApiInfo](../../models/operations/vciofferinfoapiinfo.md)     | :heavy_minus_sign:                                                                   | N/A                                                                                  |