<!-- Start SDK Example Usage [usage] -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: process.env["FLUIDAPI_BEARER_AUTH"] ?? "",
});

async function run() {
  const result = await fluidapi.metadata.healthCheck();

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->