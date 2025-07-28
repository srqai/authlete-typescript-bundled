# AuthTokenApiFormAction

The next action that the authorization server implementation should take.

## Example Usage

```typescript
import { AuthTokenApiFormAction } from "authelete-bundled/models/operations";

let value: AuthTokenApiFormAction = "TOKEN_EXCHANGE";
```

## Values

```typescript
"INTERNAL_SERVER_ERROR" | "INVALID_CLIENT" | "BAD_REQUEST" | "PASSWORD" | "OK" | "TOKEN_EXCHANGE" | "JWT_BEARER"
```