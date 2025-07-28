# AuthTokenFailApiRequestBody

## Example Usage

```typescript
import { AuthTokenFailApiRequestBody } from "authelete-bundled/models/operations";

let value: AuthTokenFailApiRequestBody = {
  ticket: "<value>",
  reason: "UNKNOWN",
};
```

## Fields

| Field                                                                                  | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `ticket`                                                                               | *string*                                                                               | :heavy_check_mark:                                                                     | The ticket issued from Authlete `/auth/token` API.<br/>                                |
| `reason`                                                                               | [operations.AuthTokenFailApiReason](../../models/operations/authtokenfailapireason.md) | :heavy_check_mark:                                                                     | The reason of the failure of the token request.<br/>                                   |