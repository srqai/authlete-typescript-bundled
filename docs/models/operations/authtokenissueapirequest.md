# AuthTokenIssueApiRequest

## Example Usage

```typescript
import { AuthTokenIssueApiRequest } from "authelete-bundled/models/operations";

let value: AuthTokenIssueApiRequest = {
  serviceId: "<id>",
  requestBody: {
    ticket: "<value>",
    subject: "<value>",
  },
};
```

## Fields

| Field                                                                                              | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                        | *string*                                                                                           | :heavy_check_mark:                                                                                 | A service ID.                                                                                      |
| `requestBody`                                                                                      | [operations.AuthTokenIssueApiRequestBody](../../models/operations/authtokenissueapirequestbody.md) | :heavy_check_mark:                                                                                 | N/A                                                                                                |