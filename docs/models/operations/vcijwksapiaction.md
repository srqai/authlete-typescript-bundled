# VciJwksApiAction

The next action that the implementation of the JWK Set document
endpoint of the credential issuer should take after getting a
response from Authlete's `/vci/jwks` API.


## Example Usage

```typescript
import { VciJwksApiAction } from "authelete-bundled/models/operations";

let value: VciJwksApiAction = "OK";
```

## Values

```typescript
"OK" | "NOT_FOUND" | "INTERNAL_SERVER_ERROR"
```