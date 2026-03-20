# Session

## Overview

Public — User session lifecycle (exchange + refresh)

### Available Operations

* [exchangeBootstrapToken](#exchangebootstraptoken) - Exchange bootstrap token for user session
* [refreshUserSession](#refreshusersession) - Renew user session (refresh token)

## exchangeBootstrapToken

Exchanges the short-lived bootstrap JWT issued by `POST /users/token` for a
Hydra-managed session token pair (`access_token` + `refresh_token`).

The bootstrap token is **single-use**: a second call with the same token
returns `401 invalid_grant`. Claims from the bootstrap token (workspace_id,
tenant_id, user_id, etc.) are forwarded into the Hydra session via the
server-side authorization code flow.

The resulting `refresh_token` can be renewed via `POST /users/token/refresh`.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="exchangeBootstrapToken" method="post" path="/users/token/exchange" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.session.exchangeBootstrapToken({
    token: "eyJhbGciOiJSUzI1NiIsImtpZCI6Ik9UO...",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { sessionExchangeBootstrapToken } from "fluidapi/funcs/session-exchange-bootstrap-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await sessionExchangeBootstrapToken(fluidapi, {
    token: "eyJhbGciOiJSUzI1NiIsImtpZCI6Ik9UO...",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("sessionExchangeBootstrapToken failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.ExchangeRequest](../../models/exchange-request.md)                                                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.SessionTokenData](../../models/session-token-data.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.OAuth2ErrorResponse | 400, 401                   | application/json           |
| errors.OAuth2ErrorResponse | 502                        | application/json           |
| errors.SDKDefaultError     | 4XX, 5XX                   | \*/\*                      |

## refreshUserSession

Exchanges a Hydra refresh token for a new session token pair
(`access_token` + `refresh_token`).

The `fluid-user-session` client credentials are handled server-side.
Browsers and mobile clients must **not** hold or send the client secret —
only the `refresh_token` is required.


### Example Usage: invalid_body

<!-- UsageSnippet language="typescript" operationID="refreshUserSession" method="post" path="/users/token/refresh" example="invalid_body" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.session.refreshUserSession({
    refreshToken: "ory_rt_...",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { sessionRefreshUserSession } from "fluidapi/funcs/session-refresh-user-session.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await sessionRefreshUserSession(fluidapi, {
    refreshToken: "ory_rt_...",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("sessionRefreshUserSession failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_grant

<!-- UsageSnippet language="typescript" operationID="refreshUserSession" method="post" path="/users/token/refresh" example="invalid_grant" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.session.refreshUserSession({
    refreshToken: "ory_rt_...",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { sessionRefreshUserSession } from "fluidapi/funcs/session-refresh-user-session.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await sessionRefreshUserSession(fluidapi, {
    refreshToken: "ory_rt_...",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("sessionRefreshUserSession failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.RefreshRequest](../../models/refresh-request.md)                                                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.SessionTokenData](../../models/session-token-data.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.OAuth2ErrorResponse | 400, 401                   | application/json           |
| errors.OAuth2ErrorResponse | 502                        | application/json           |
| errors.SDKDefaultError     | 4XX, 5XX                   | \*/\*                      |