# ClientGrantedScopesDeleteApiRequest

## Example Usage

```typescript
import { ClientGrantedScopesDeleteApiRequest } from "authelete-bundled/models/operations";

let value: ClientGrantedScopesDeleteApiRequest = {
  subject: "<value>",
  serviceId: "<id>",
  clientId: "<id>",
};
```

## Fields

| Field                           | Type                            | Required                        | Description                     |
| ------------------------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| `subject`                       | *string*                        | :heavy_check_mark:              | Unique user ID of an end-user.<br/> |
| `serviceId`                     | *string*                        | :heavy_check_mark:              | A service ID.                   |
| `clientId`                      | *string*                        | :heavy_check_mark:              | A client ID.<br/>               |