# BackchannelAuthenticationIssueApiRequestBody

## Example Usage

```typescript
import { BackchannelAuthenticationIssueApiRequestBody } from "authelete-bundled/models/operations";

let value: BackchannelAuthenticationIssueApiRequestBody = {
  ticket: "<value>",
};
```

## Fields

| Field                                                                 | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `ticket`                                                              | *string*                                                              | :heavy_check_mark:                                                    | The ticket issued from Authlete's `/backchannel/authentication` API.<br/> |