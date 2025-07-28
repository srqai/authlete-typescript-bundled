# FederationRegistrationApiFormRequest

## Example Usage

```typescript
import { FederationRegistrationApiFormRequest } from "authelete-bundled/models/operations";

let value: FederationRegistrationApiFormRequest = {
  serviceId: "<id>",
  requestBody: {
    clientLocked: true,
  },
};
```

## Fields

| Field                                                                                                                      | Type                                                                                                                       | Required                                                                                                                   | Description                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                                | *string*                                                                                                                   | :heavy_check_mark:                                                                                                         | A service ID.                                                                                                              |
| `requestBody`                                                                                                              | [operations.FederationRegistrationApiFormRequestBody](../../models/operations/federationregistrationapiformrequestbody.md) | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |