# AuthTokenGetListApiRequest

## Example Usage

```typescript
import { AuthTokenGetListApiRequest } from "authelete-bundled/models/operations";

let value: AuthTokenGetListApiRequest = {
  serviceId: "<id>",
};
```

## Fields

| Field                                                              | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `clientIdentifier`                                                 | *string*                                                           | :heavy_minus_sign:                                                 | Client Identifier (client ID or client ID alias).<br/>             |
| `subject`                                                          | *string*                                                           | :heavy_minus_sign:                                                 | Unique user ID.<br/>                                               |
| `start`                                                            | *number*                                                           | :heavy_minus_sign:                                                 | Start index of search results (inclusive). The default value is 0. |
| `end`                                                              | *number*                                                           | :heavy_minus_sign:                                                 | End index of search results (exclusive). The default value is 5.<br/> |
| `serviceId`                                                        | *string*                                                           | :heavy_check_mark:                                                 | A service ID.                                                      |