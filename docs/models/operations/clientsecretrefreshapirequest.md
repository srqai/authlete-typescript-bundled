# ClientSecretRefreshApiRequest

## Example Usage

```typescript
import { ClientSecretRefreshApiRequest } from "authelete-bundled/models/operations";

let value: ClientSecretRefreshApiRequest = {
  serviceId: "<id>",
  clientIdentifier: "<value>",
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `serviceId`                                        | *string*                                           | :heavy_check_mark:                                 | A service ID.                                      |
| `clientIdentifier`                                 | *string*                                           | :heavy_check_mark:                                 | The client ID or the client ID alias of a client.<br/> |