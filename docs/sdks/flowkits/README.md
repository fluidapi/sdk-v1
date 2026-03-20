# Flowkits

## Overview

Available flowkit definitions (catalog)

### Available Operations

* [listFlowkits](#listflowkits) - List available flowkits

## listFlowkits

Returns the catalog of flowkit definitions available to the authenticated tenant.

> **Status**: endpoint reservado — documentação detalhada pendente.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="listFlowkits" method="get" path="/{tenant}/v1/flowkits" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await fluidapi.flowkits.listFlowkits({
    tenant: "contaazul",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { flowkitsListFlowkits } from "fluidapi/funcs/flowkits-list-flowkits.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await flowkitsListFlowkits(fluidapi, {
    tenant: "contaazul",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("flowkitsListFlowkits failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListFlowkitsRequest](../../models/operations/list-flowkits-request.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.FlowkitListResponse](../../models/flowkit-list-response.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |