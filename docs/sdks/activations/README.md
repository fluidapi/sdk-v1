# Activations

## Overview

Activated flowkit instances — list, activate and delete

### Available Operations

* [listFlowkitActivations](#listflowkitactivations) - List activated flowkits
* [deleteFlowkitActivation](#deleteflowkitactivation) - Delete a flowkit activation
* [activateFlowkit](#activateflowkit) - Activate a flowkit integration

## listFlowkitActivations

Returns all flowkit activations for the authenticated tenant.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="listFlowkitActivations" method="get" path="/{tenant}/v1/flowkits/activations" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await fluidapi.activations.listFlowkitActivations({
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
import { activationsListFlowkitActivations } from "fluidapi/funcs/activations-list-flowkit-activations.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await activationsListFlowkitActivations(fluidapi, {
    tenant: "contaazul",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("activationsListFlowkitActivations failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListFlowkitActivationsRequest](../../models/operations/list-flowkit-activations-request.md)                                                                        | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.FlowkitActivationListResponse](../../models/flowkit-activation-list-response.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |

## deleteFlowkitActivation

Removes an active flowkit instance for the authenticated tenant.

The activation to be removed is identified by query parameters.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteFlowkitActivation" method="delete" path="/{tenant}/v1/flowkits/activations" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  await fluidapi.activations.deleteFlowkitActivation({
    tenant: "contaazul",
    id: "bling-linx-1.0.7",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { activationsDeleteFlowkitActivation } from "fluidapi/funcs/activations-delete-flowkit-activation.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await activationsDeleteFlowkitActivation(fluidapi, {
    tenant: "contaazul",
    id: "bling-linx-1.0.7",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("activationsDeleteFlowkitActivation failed:", res.error);
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

**Promise\<void\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |

## activateFlowkit

Activates a flowkit for the given tenant and integration, supplying
connector credentials and per-tenant runtime data.

The `key` query parameter identifies the flowkit definition to activate.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="activateFlowkit" method="post" path="/{tenant}/v1/flowkits/{integration}/activate" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await fluidapi.activations.activateFlowkit({
    tenant: "contaazul",
    integration: "tray",
    key: "dab7e862-5899-4993-b50b-2fe8c4535b8e",
    body: {
      credentials: {
        "url": "https://1225878.commercesuite.com.br",
        "code": "504c234370fd5bc6224ad99e154c039fbecbd9d893fajsdoi78y87sdysj9sdd",
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
import { activationsActivateFlowkit } from "fluidapi/funcs/activations-activate-flowkit.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await activationsActivateFlowkit(fluidapi, {
    tenant: "contaazul",
    integration: "tray",
    key: "dab7e862-5899-4993-b50b-2fe8c4535b8e",
    body: {
      credentials: {
        "url": "https://1225878.commercesuite.com.br",
        "code": "504c234370fd5bc6224ad99e154c039fbecbd9d893fajsdoi78y87sdysj9sdd",
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
    console.log("activationsActivateFlowkit failed:", res.error);
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

**Promise\<[models.FlowkitActivationRecord](../../models/flowkit-activation-record.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |