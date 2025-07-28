# AuthTokenUpdateApiFormAuthorizationDetails

The authorization details. This represents the value of the `authorization_details`
request parameter in the preceding device authorization request which is defined in
"OAuth 2.0 Rich Authorization Requests".


## Example Usage

```typescript
import { AuthTokenUpdateApiFormAuthorizationDetails } from "authelete-bundled/models/operations";

let value: AuthTokenUpdateApiFormAuthorizationDetails = {};
```

## Fields

| Field                                                                                                  | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `elements`                                                                                             | [operations.AuthTokenUpdateApiFormElement](../../models/operations/authtokenupdateapiformelement.md)[] | :heavy_minus_sign:                                                                                     | Elements of this authorization details.<br/>                                                           |