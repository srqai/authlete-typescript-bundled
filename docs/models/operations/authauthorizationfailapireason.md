# AuthAuthorizationFailApiReason

The reason of the failure of the authorization request.
For more details, see [NO_INTERACTION] in the description of `/auth/authorization` API.


## Example Usage

```typescript
import { AuthAuthorizationFailApiReason } from "authelete-bundled/models/operations";

let value: AuthAuthorizationFailApiReason = "DIFFERENT_SUBJECT";
```

## Values

```typescript
"UNKNOWN" | "NOT_LOGGED_IN" | "MAX_AGE_NOT_SUPPORTED" | "EXCEEDS_MAX_AGE" | "DIFFERENT_SUBJECT" | "ACR_NOT_SATISFIED" | "DENIED" | "SERVER_ERROR" | "NOT_AUTHENTICATED" | "ACCOUNT_SELECTION_REQUIRED" | "CONSENT_REQUIRED" | "INTERACTION_REQUIRED" | "INVALID_TARGET"
```