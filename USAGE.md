<!-- Start SDK Example Usage [usage] -->
```typescript
import { AutheleteBundled } from "authelete-bundled";

const autheleteBundled = new AutheleteBundled({
  security: {
    authlete: process.env["AUTHELETEBUNDLED_AUTHLETE"] ?? "",
  },
});

async function run() {
  const result = await autheleteBundled.serviceManagement.serviceGetApi({
    serviceId: "<id>",
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->