<!-- Start SDK Example Usage [usage] -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.metadata.healthCheck();

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->