# AuthTokenDeleteApiRequest

## Example Usage

```typescript
import { AuthTokenDeleteApiRequest } from "authelete-bundled/models/operations";

let value: AuthTokenDeleteApiRequest = {
  serviceId: "<id>",
  accessTokenIdentifier: "<value>",
};
```

## Fields

| Field                                                                                                                                      | Type                                                                                                                                       | Required                                                                                                                                   | Description                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `serviceId`                                                                                                                                | *string*                                                                                                                                   | :heavy_check_mark:                                                                                                                         | A service ID.                                                                                                                              |
| `accessTokenIdentifier`                                                                                                                    | *string*                                                                                                                                   | :heavy_check_mark:                                                                                                                         | The identifier of an existing access token. The identifier is the value of the access token<br/>or the value of the hash of the access token.<br/> |