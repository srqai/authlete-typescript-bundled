# VciSingleIssueApiResponse

## Example Usage

```typescript
import { VciSingleIssueApiResponse } from "authelete-bundled/models/operations";

let value: VciSingleIssueApiResponse = {};
```

## Fields

| Field                                                                                          | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `resultCode`                                                                                   | *string*                                                                                       | :heavy_minus_sign:                                                                             | The code which represents the result of the API call.                                          |
| `resultMessage`                                                                                | *string*                                                                                       | :heavy_minus_sign:                                                                             | A short message which explains the result of the API call.                                     |
| `action`                                                                                       | [operations.VciSingleIssueApiAction](../../models/operations/vcisingleissueapiaction.md)       | :heavy_minus_sign:                                                                             | The next action that the implementation of the credential endpoint<br/>should take.<br/>       |
| `responseContent`                                                                              | *string*                                                                                       | :heavy_minus_sign:                                                                             | The content of the response that the implementation of the credential<br/>endpoint should return.<br/> |
| `transactionId`                                                                                | *string*                                                                                       | :heavy_minus_sign:                                                                             | The issued transaction ID.<br/>                                                                |