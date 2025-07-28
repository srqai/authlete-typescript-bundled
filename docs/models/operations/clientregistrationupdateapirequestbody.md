# ClientRegistrationUpdateApiRequestBody

## Example Usage

```typescript
import { ClientRegistrationUpdateApiRequestBody } from "authelete-bundled/models/operations";

let value: ClientRegistrationUpdateApiRequestBody = {
  clientId: "<id>",
  token: "<value>",
  json: "{key: 7112400702100740, key1: null, key2: \"<value>\"}",
};
```

## Fields

| Field                                                                                                                                                          | Type                                                                                                                                                           | Required                                                                                                                                                       | Description                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `clientId`                                                                                                                                                     | *string*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                             | Client ID.<br/>                                                                                                                                                |
| `token`                                                                                                                                                        | *string*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                             | Client registration access token.<br/>                                                                                                                         |
| `json`                                                                                                                                                         | *string*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                             | Client metadata in JSON format that complies with [RFC 7591](https://datatracker.ietf.org/doc/html/rfc7591)<br/>(OAuth 2.0 Dynamic Client Registration Protocol).<br/> |