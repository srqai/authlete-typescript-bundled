# ClientAuthorizationGetListApiRequest

## Example Usage

```typescript
import { ClientAuthorizationGetListApiRequest } from "authelete-bundled/models/operations";

let value: ClientAuthorizationGetListApiRequest = {
  subject: "<value>",
  serviceId: "<id>",
};
```

## Fields

| Field                                                              | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `subject`                                                          | *string*                                                           | :heavy_check_mark:                                                 | Unique user ID of an end-user.<br/>                                |
| `developer`                                                        | *string*                                                           | :heavy_minus_sign:                                                 | Unique ID of a client developer.<br/>                              |
| `start`                                                            | *number*                                                           | :heavy_minus_sign:                                                 | Start index of search results (inclusive). The default value is 0. |
| `end`                                                              | *number*                                                           | :heavy_minus_sign:                                                 | End index of search results (exclusive). The default value is 5.<br/> |
| `serviceId`                                                        | *string*                                                           | :heavy_check_mark:                                                 | A service ID.                                                      |