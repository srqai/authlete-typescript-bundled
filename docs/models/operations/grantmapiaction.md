# GrantMApiAction

The next action that the authorization server implementation should take.

## Example Usage

```typescript
import { GrantMApiAction } from "authelete-bundled/models/operations";

let value: GrantMApiAction = "NO_CONTENT";
```

## Values

```typescript
"OK" | "NO_CONTENT" | "UNAUTHORIZED" | "FORBIDDEN" | "NOT_FOUND" | "CALLER_ERROR" | "AUTHLETE_ERROR"
```