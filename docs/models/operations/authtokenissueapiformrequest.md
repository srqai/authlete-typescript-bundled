# AuthTokenIssueApiFormRequest

## Example Usage

```typescript
import { AuthTokenIssueApiFormRequest } from "authelete-bundled/models/operations";

let value: AuthTokenIssueApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: false,
  },
};
```

## Fields

| Field                                                                                                      | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                | *string*                                                                                                   | :heavy_check_mark:                                                                                         | A service ID.                                                                                              |
| `requestBody`                                                                                              | [operations.AuthTokenIssueApiFormRequestBody](../../models/operations/authtokenissueapiformrequestbody.md) | :heavy_check_mark:                                                                                         | N/A                                                                                                        |