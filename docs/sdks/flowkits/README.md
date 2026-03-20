# Flowkits

## Overview

Operations related to Flowkit lifecycle management.

### Available Operations

* [activateFlowkit](#activateflowkit) - Activate Flowkit
* [listFlowkitActivations](#listflowkitactivations) - List active Flowkits
* [deleteFlowkitActivation](#deleteflowkitactivation) - Delete Flowkit activation

## activateFlowkit

Activates a Flowkit for the Conta Azul integration using the provided
connector credentials and tenant/user context metadata.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="activateFlowkit" method="post" path="/contaazul/v1/flowkits/activations" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await fluidapi.flowkits.activateFlowkit({
    key: "dab7e862-5899-4993-b50b-2fe8c4535b8e",
    body: {
      credentials: {
        url: "https://1225878.commercesuite.com.br",
        code: "504c234370fd5bc6224ad99e154c039fbecbd9d893fajsdoi78y87sdysj9sdd",
      },
      data: {
        identifier: "loja01",
        xTenantId: "3363001",
        xUserId: "58139234",
        xEmail: "1d46cf93-68c7-4106-345s-43f147ecdd67@devportal.com",
      },
    },
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { flowkitsActivateFlowkit } from "fluidapi/funcs/flowkits-activate-flowkit.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await flowkitsActivateFlowkit(fluidapi, {
    key: "dab7e862-5899-4993-b50b-2fe8c4535b8e",
    body: {
      credentials: {
        url: "https://1225878.commercesuite.com.br",
        code: "504c234370fd5bc6224ad99e154c039fbecbd9d893fajsdoi78y87sdysj9sdd",
      },
      data: {
        identifier: "loja01",
        xTenantId: "3363001",
        xUserId: "58139234",
        xEmail: "1d46cf93-68c7-4106-345s-43f147ecdd67@devportal.com",
      },
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("flowkitsActivateFlowkit failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ActivateFlowkitRequest](../../models/operations/activate-flowkit-request.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.FlowkitActivation](../../models/flowkit-activation.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.ErrorResponse   | 400, 401               | application/json       |
| errors.ErrorResponse   | 500                    | application/json       |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |

## listFlowkitActivations

Returns the currently activated Flowkits.

This operation is currently documented with a mock response so the SDK
can be generated and consumed by the client team before the final API
contract is available.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="listFlowkitActivations" method="get" path="/contaazul/v1/flowkits/activations" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await fluidapi.flowkits.listFlowkitActivations();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { flowkitsListFlowkitActivations } from "fluidapi/funcs/flowkits-list-flowkit-activations.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await flowkitsListFlowkitActivations(fluidapi);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("flowkitsListFlowkitActivations failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.ListFlowkitActivationsResponse](../../models/list-flowkit-activations-response.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.ErrorResponse   | 401                    | application/json       |
| errors.ErrorResponse   | 500                    | application/json       |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |

## deleteFlowkitActivation

Deletes an activated Flowkit by its activation identifier.

This operation is currently scaffolded for SDK generation and uses a
mock success response.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteFlowkitActivation" method="delete" path="/contaazul/v1/flowkits/activations/{activationId}" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await fluidapi.flowkits.deleteFlowkitActivation({
    activationId: "bling-linx-1.0.7",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { flowkitsDeleteFlowkitActivation } from "fluidapi/funcs/flowkits-delete-flowkit-activation.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await flowkitsDeleteFlowkitActivation(fluidapi, {
    activationId: "bling-linx-1.0.7",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("flowkitsDeleteFlowkitActivation failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteFlowkitActivationRequest](../../models/operations/delete-flowkit-activation-request.md)                                                                      | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.DeleteFlowkitActivationResponse](../../models/delete-flowkit-activation-response.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.ErrorResponse   | 400, 401, 404          | application/json       |
| errors.ErrorResponse   | 500                    | application/json       |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |