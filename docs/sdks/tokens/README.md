# Tokens

## Overview

Public — Token issuance for tenants

### Available Operations

* [issueToken](#issuetoken) - Issue access token (client_credentials)
* [issueFluidToken](#issuefluidtoken) - Issue Fluid-signed M2M token
* [issueUserToken](#issueusertoken) - Issue end-user token

## issueToken

Standard OAuth2 token endpoint. Performs a `client_credentials` grant
against the Authorization Server and returns the access token (JWT).

The OAuth2 client must be registered first via
`POST /v1/tenants/{tenant_id}/credentials`.

### Scope reduction

By default the token is issued with all scopes configured for the tenant.
You can request a subset by passing `scope` in the form body.
Requesting a scope not in the tenant's allowlist returns `400 invalid_scope`.

**Available scopes:** `fluid:api`


### Example Usage: default_scope

<!-- UsageSnippet language="typescript" operationID="issueToken" method="post" path="/oauth2/token" example="default_scope" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueToken } from "fluidapi/funcs/tokens-issue-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueToken failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_request

<!-- UsageSnippet language="typescript" operationID="issueToken" method="post" path="/oauth2/token" example="invalid_request" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueToken } from "fluidapi/funcs/tokens-issue-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueToken failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_scope

<!-- UsageSnippet language="typescript" operationID="issueToken" method="post" path="/oauth2/token" example="invalid_scope" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueToken } from "fluidapi/funcs/tokens-issue-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueToken failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_tenant_id

<!-- UsageSnippet language="typescript" operationID="issueToken" method="post" path="/oauth2/token" example="invalid_tenant_id" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueToken } from "fluidapi/funcs/tokens-issue-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueToken failed:", res.error);
  }
}

run();
```
### Example Usage: reduced_scope

<!-- UsageSnippet language="typescript" operationID="issueToken" method="post" path="/oauth2/token" example="reduced_scope" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueToken } from "fluidapi/funcs/tokens-issue-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueToken failed:", res.error);
  }
}

run();
```
### Example Usage: unsupported_grant_type

<!-- UsageSnippet language="typescript" operationID="issueToken" method="post" path="/oauth2/token" example="unsupported_grant_type" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueToken } from "fluidapi/funcs/tokens-issue-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueToken failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.IssueTokenRequest](../../models/issue-token-request.md)                                                                                                                | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.IssueTokenResponse](../../models/operations/issue-token-response.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.ErrorResponse        | 400, 401                    | application/json            |
| errors.ErrorResponse        | 502                         | application/json            |
| errors.FluidapiDefaultError | 4XX, 5XX                    | \*/\*                       |

## issueFluidToken

Validates client credentials against the Authorization Server and then
generates a JWT signed by Fluid.

This endpoint coexists with `/oauth2/token`.
Use `/oauth2/token` when you want the standard Hydra-backed token flow.
Use `/oauth2/token-fluid` when you need a Fluid-signed JWT carrying
`workspace_id`, `tenant_id`, `client_id`, and `credential_type` claims for M2M calls.


### Example Usage: invalid_request

<!-- UsageSnippet language="typescript" operationID="issueFluidToken" method="post" path="/oauth2/token-fluid" example="invalid_request" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueFluidToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueFluidToken } from "fluidapi/funcs/tokens-issue-fluid-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueFluidToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueFluidToken failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_scope

<!-- UsageSnippet language="typescript" operationID="issueFluidToken" method="post" path="/oauth2/token-fluid" example="invalid_scope" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueFluidToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueFluidToken } from "fluidapi/funcs/tokens-issue-fluid-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueFluidToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueFluidToken failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_tenant_id

<!-- UsageSnippet language="typescript" operationID="issueFluidToken" method="post" path="/oauth2/token-fluid" example="invalid_tenant_id" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueFluidToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueFluidToken } from "fluidapi/funcs/tokens-issue-fluid-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueFluidToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueFluidToken failed:", res.error);
  }
}

run();
```
### Example Usage: unsupported_grant_type

<!-- UsageSnippet language="typescript" operationID="issueFluidToken" method="post" path="/oauth2/token-fluid" example="unsupported_grant_type" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueFluidToken({
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueFluidToken } from "fluidapi/funcs/tokens-issue-fluid-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueFluidToken(fluidapi, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueFluidToken failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.IssueTokenRequest](../../models/issue-token-request.md)                                                                                                                | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.IssueFluidTokenResponse](../../models/operations/issue-fluid-token-response.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.ErrorResponse        | 400, 401                    | application/json            |
| errors.ErrorResponse        | 502                         | application/json            |
| errors.FluidapiDefaultError | 4XX, 5XX                    | \*/\*                       |

## issueUserToken

Issues a JWT for an end user (workspace user or customer user).

Supported authentication modes:
- `Authorization: Bearer <m2m_token>` — preferred. The token must be a
  Fluid-signed M2M JWT with `scope` including `fluid:api`.
  Canonical first-access provisioning via external lookup/create is only
  available in this mode.
- HTTP Basic Auth with `client_id` + `client_secret`.
  In this mode the service does not perform canonical lookup/create.

If `customer_external_id` is present, the JWT is issued with `scope: customer`.
Otherwise it is issued with `scope: workspace`.

When canonical first-access provisioning is enabled, `email` is required
so the service can lookup or create the canonical user before issuing the token.

When canonical provisioning is disabled by server configuration, the
service may materialize local IAM context by assuming `external_id` is
already the canonical `user_id`.


### Example Usage: email_required

<!-- UsageSnippet language="typescript" operationID="issueUserToken" method="post" path="/users/token" example="email_required" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueUserToken({
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 3600,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueUserToken } from "fluidapi/funcs/tokens-issue-user-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueUserToken(fluidapi, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 3600,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueUserToken failed:", res.error);
  }
}

run();
```
### Example Usage: external_id_required

<!-- UsageSnippet language="typescript" operationID="issueUserToken" method="post" path="/users/token" example="external_id_required" -->
```typescript
import { Fluidapi } from "fluidapi";

const fluidapi = new Fluidapi();

async function run() {
  const result = await fluidapi.tokens.issueUserToken({
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 3600,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { FluidapiCore } from "fluidapi/core.js";
import { tokensIssueUserToken } from "fluidapi/funcs/tokens-issue-user-token.js";

// Use `FluidapiCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const fluidapi = new FluidapiCore();

async function run() {
  const res = await tokensIssueUserToken(fluidapi, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 3600,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueUserToken failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.UserTokenRequest](../../models/user-token-request.md)                                                                                                                  | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.IssueUserTokenResponse](../../models/operations/issue-user-token-response.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.ErrorResponse        | 400, 401, 403, 404, 409     | application/json            |
| errors.ErrorResponse        | 502                         | application/json            |
| errors.FluidapiDefaultError | 4XX, 5XX                    | \*/\*                       |