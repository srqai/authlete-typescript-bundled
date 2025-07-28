# PushedAuthReqApiAction

The next action that the authorization server implementation should take. Any other value other than "CREATED" should be handled as unsuccessful result.

## Example Usage

```typescript
import { PushedAuthReqApiAction } from "authelete-bundled/models/operations";

let value: PushedAuthReqApiAction = "FORBIDDEN";
```

## Values

```typescript
"CREATED" | "BAD_REQUEST" | "UNAUTHORIZED" | "FORBIDDEN" | "PAYLOAD_TOO_LARGE" | "INTERNAL_SERVER_ERROR"
```