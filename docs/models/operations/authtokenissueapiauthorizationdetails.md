# AuthTokenIssueApiAuthorizationDetails

The authorization details. This represents the value of the `authorization_details`
request parameter in the preceding device authorization request which is defined in
"OAuth 2.0 Rich Authorization Requests".


## Example Usage

```typescript
import { AuthTokenIssueApiAuthorizationDetails } from "authelete-bundled/models/operations";

let value: AuthTokenIssueApiAuthorizationDetails = {};
```

## Fields

| Field                                                                                        | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `elements`                                                                                   | [operations.AuthTokenIssueApiElement](../../models/operations/authtokenissueapielement.md)[] | :heavy_minus_sign:                                                                           | Elements of this authorization details.<br/>                                                 |