# AuthAuthorizationIssueApiRequest

## Example Usage

```typescript
import { AuthAuthorizationIssueApiRequest } from "authelete-bundled/models/operations";

let value: AuthAuthorizationIssueApiRequest = {
  serviceId: "<id>",
  requestBody: {
    ticket: "<value>",
    subject: "<value>",
  },
};
```

## Fields

| Field                                                                                                              | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                                        | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | A service ID.                                                                                                      |
| `requestBody`                                                                                                      | [operations.AuthAuthorizationIssueApiRequestBody](../../models/operations/authauthorizationissueapirequestbody.md) | :heavy_check_mark:                                                                                                 | N/A                                                                                                                |