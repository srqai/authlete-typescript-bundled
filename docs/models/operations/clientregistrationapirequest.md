# ClientRegistrationApiRequest

## Example Usage

```typescript
import { ClientRegistrationApiRequest } from "authelete-bundled/models/operations";

let value: ClientRegistrationApiRequest = {
  serviceId: "<id>",
  requestBody: {
    json: "{key: 4973218959062003, key1: null, key2: \"<value>\"}",
  },
};
```

## Fields

| Field                                                                                                      | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `serviceId`                                                                                                | *string*                                                                                                   | :heavy_check_mark:                                                                                         | A service ID.                                                                                              |
| `requestBody`                                                                                              | [operations.ClientRegistrationApiRequestBody](../../models/operations/clientregistrationapirequestbody.md) | :heavy_check_mark:                                                                                         | N/A                                                                                                        |