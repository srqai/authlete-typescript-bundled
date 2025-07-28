# VciBatchIssueApiResponse

## Example Usage

```typescript
import { VciBatchIssueApiResponse } from "authelete-bundled/models/operations";

let value: VciBatchIssueApiResponse = {};
```

## Fields

| Field                                                                                                | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `resultCode`                                                                                         | *string*                                                                                             | :heavy_minus_sign:                                                                                   | The code which represents the result of the API call.                                                |
| `resultMessage`                                                                                      | *string*                                                                                             | :heavy_minus_sign:                                                                                   | A short message which explains the result of the API call.                                           |
| `action`                                                                                             | [operations.VciBatchIssueApiAction](../../models/operations/vcibatchissueapiaction.md)               | :heavy_minus_sign:                                                                                   | The next action that the implementation of the batch credential<br/>endpoint should take.<br/>       |
| `responseContent`                                                                                    | *string*                                                                                             | :heavy_minus_sign:                                                                                   | The content of the response that the implementation of the batch<br/>credential endpoint should return.<br/> |