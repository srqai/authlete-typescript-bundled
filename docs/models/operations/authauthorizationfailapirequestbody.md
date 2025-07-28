# AuthAuthorizationFailApiRequestBody

## Example Usage

```typescript
import { AuthAuthorizationFailApiRequestBody } from "authelete-bundled/models/operations";

let value: AuthAuthorizationFailApiRequestBody = {
  ticket: "<value>",
  reason: "ACR_NOT_SATISFIED",
};
```

## Fields

| Field                                                                                                                                            | Type                                                                                                                                             | Required                                                                                                                                         | Description                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ticket`                                                                                                                                         | *string*                                                                                                                                         | :heavy_check_mark:                                                                                                                               | The ticket issued from Authlete `/auth/authorization` API.<br/>                                                                                  |
| `reason`                                                                                                                                         | [operations.AuthAuthorizationFailApiReason](../../models/operations/authauthorizationfailapireason.md)                                           | :heavy_check_mark:                                                                                                                               | The reason of the failure of the authorization request.<br/>For more details, see [NO_INTERACTION] in the description of `/auth/authorization` API.<br/> |
| `description`                                                                                                                                    | *string*                                                                                                                                         | :heavy_minus_sign:                                                                                                                               | The custom description about the authorization failure.<br/>                                                                                     |