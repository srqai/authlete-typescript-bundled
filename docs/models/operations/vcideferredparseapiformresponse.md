# VciDeferredParseApiFormResponse

## Example Usage

```typescript
import { VciDeferredParseApiFormResponse } from "authelete-bundled/models/operations";

let value: VciDeferredParseApiFormResponse = {};
```

## Fields

| Field                                                                                                | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `resultCode`                                                                                         | *string*                                                                                             | :heavy_minus_sign:                                                                                   | The code which represents the result of the API call.                                                |
| `resultMessage`                                                                                      | *string*                                                                                             | :heavy_minus_sign:                                                                                   | A short message which explains the result of the API call.                                           |
| `action`                                                                                             | [operations.VciDeferredParseApiFormAction](../../models/operations/vcideferredparseapiformaction.md) | :heavy_minus_sign:                                                                                   | The next action that the deferred credential endpoint should take.                                   |
| `responseContent`                                                                                    | *string*                                                                                             | :heavy_minus_sign:                                                                                   | The content of the response to the request sender.                                                   |
| `info`                                                                                               | [operations.VciDeferredParseApiFormInfo](../../models/operations/vcideferredparseapiforminfo.md)     | :heavy_minus_sign:                                                                                   | Information about the credential request bound to the transaction ID.                                |