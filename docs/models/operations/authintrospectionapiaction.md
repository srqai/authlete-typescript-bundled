# AuthIntrospectionApiAction

The next action that the authorization server implementation should take.

## Example Usage

```typescript
import { AuthIntrospectionApiAction } from "authelete-bundled/models/operations";

let value: AuthIntrospectionApiAction = "BAD_REQUEST";
```

## Values

```typescript
"INTERNAL_SERVER_ERROR" | "BAD_REQUEST" | "UNAUTHORIZED" | "FORBIDDEN" | "OK"
```