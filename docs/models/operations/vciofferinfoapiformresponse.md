# VciOfferInfoApiFormResponse

## Example Usage

```typescript
import { VciOfferInfoApiFormResponse } from "authelete-bundled/models/operations";

let value: VciOfferInfoApiFormResponse = {};
```

## Fields

| Field                                                                                        | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `resultCode`                                                                                 | *string*                                                                                     | :heavy_minus_sign:                                                                           | The code which represents the result of the API call.                                        |
| `resultMessage`                                                                              | *string*                                                                                     | :heavy_minus_sign:                                                                           | A short message which explains the result of the API call.                                   |
| `action`                                                                                     | [operations.VciOfferInfoApiFormAction](../../models/operations/vciofferinfoapiformaction.md) | :heavy_minus_sign:                                                                           | The result of the `/vci/offer/info` API call.                                                |
| `info`                                                                                       | [operations.VciOfferInfoApiFormInfo](../../models/operations/vciofferinfoapiforminfo.md)     | :heavy_minus_sign:                                                                           | N/A                                                                                          |