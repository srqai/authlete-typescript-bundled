# ClientSecretUpdateApiRequestBody

## Example Usage

```typescript
import { ClientSecretUpdateApiRequestBody } from "authelete-bundled/models/operations";

let value: ClientSecretUpdateApiRequestBody = {
  clientSecret: "<value>",
};
```

## Fields

| Field                                                                                                                                                         | Type                                                                                                                                                          | Required                                                                                                                                                      | Description                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `clientSecret`                                                                                                                                                | *string*                                                                                                                                                      | :heavy_check_mark:                                                                                                                                            | The new value of the client secret. Valid characters for a client secret are `A-Z`, `a-z`, `0-9`,<br/>`-`, and `_`. The maximum length of a client secret is 86.<br/> |