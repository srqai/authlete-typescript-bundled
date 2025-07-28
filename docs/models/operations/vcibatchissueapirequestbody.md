# VciBatchIssueApiRequestBody

## Example Usage

```typescript
import { VciBatchIssueApiRequestBody } from "authelete-bundled/models/operations";

let value: VciBatchIssueApiRequestBody = {};
```

## Fields

| Field                                                                                  | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `accessToken`                                                                          | *string*                                                                               | :heavy_minus_sign:                                                                     | The access token that came along with the credential request.                          |
| `orders`                                                                               | [operations.VciBatchIssueApiOrder](../../models/operations/vcibatchissueapiorder.md)[] | :heavy_minus_sign:                                                                     | The instructions for issuance of credentials and/or transaction IDs.                   |