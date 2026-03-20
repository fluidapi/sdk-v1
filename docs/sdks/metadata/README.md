# Metadata

## Overview

Public — Metadata and health endpoints

### Available Operations

* [healthCheck](#healthcheck) - Health check
* [getJwks](#getjwks) - Get public signing keys

## healthCheck

Health check

### Example Usage

<!-- UsageSnippet language="typescript" operationID="healthCheck" method="get" path="/health" -->
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

### Standalone function

The standalone function version of this method:

```typescript
import { SDKCore } from "openapi/core.js";
import { metadataHealthCheck } from "openapi/funcs/metadata-health-check.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await metadataHealthCheck(sdk);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("metadataHealthCheck failed:", res.error);
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

**Promise\<[models.HealthResponse](../../models/health-response.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.ErrorResponse   | 503                    | application/json       |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |

## getJwks

Returns the JWKS used to validate Fluid-signed JWTs.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getJWKS" method="get" path="/.well-known/jwks.json" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.metadata.getJwks();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SDKCore } from "openapi/core.js";
import { metadataGetJwks } from "openapi/funcs/metadata-get-jwks.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await metadataGetJwks(sdk);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("metadataGetJwks failed:", res.error);
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

**Promise\<[models.JWKSet](../../models/jwk-set.md)\>**

### Errors

| Error Type             | Status Code            | Content Type           |
| ---------------------- | ---------------------- | ---------------------- |
| errors.ErrorResponse   | 503                    | application/json       |
| errors.SDKDefaultError | 4XX, 5XX               | \*/\*                  |