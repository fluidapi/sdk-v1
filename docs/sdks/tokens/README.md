# Tokens

## Overview

Public — Token issuance for tenants

### Available Operations

* [issue](#issue) - Issue M2M token (client_credentials)
* [~~issueFluidTokenLegacy~~](#issuefluidtokenlegacy) - Issue Fluid-signed M2M token (legacy) :warning: **Deprecated**
* [issueUser](#issueuser) - Issue bootstrap token for end user

## issue

OAuth2 token endpoint for M2M (machine-to-machine) access.
Only `grant_type=client_credentials` is supported.

Performs a `client_credentials` grant against the Authorization Server and
returns a Hydra-issued access token (JWT) following RFC 6749 token response format.

The OAuth2 client must be registered first via
`POST /v1/tenants/{tenant_id}/credentials`.

By default the token is issued with all scopes configured for the tenant.
You can request a subset by passing `scope`. Requesting a scope not in the
tenant's allowlist returns `400 invalid_scope`.

> **User session refresh:** use `POST /users/token/refresh` instead.
> The client secret is handled server-side and must not be sent by browsers.


### Example Usage: invalid_request

<!-- UsageSnippet language="typescript" operationID="issueM2MToken" method="post" path="/oauth2/token" example="invalid_request" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.tokens.issue({
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
import { SDKCore } from "openapi/core.js";
import { tokensIssue } from "openapi/funcs/tokens-issue.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await tokensIssue(sdk, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssue failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_scope

<!-- UsageSnippet language="typescript" operationID="issueM2MToken" method="post" path="/oauth2/token" example="invalid_scope" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.tokens.issue({
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
import { SDKCore } from "openapi/core.js";
import { tokensIssue } from "openapi/funcs/tokens-issue.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await tokensIssue(sdk, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssue failed:", res.error);
  }
}

run();
```
### Example Usage: unsupported_grant_type

<!-- UsageSnippet language="typescript" operationID="issueM2MToken" method="post" path="/oauth2/token" example="unsupported_grant_type" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.tokens.issue({
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
import { SDKCore } from "openapi/core.js";
import { tokensIssue } from "openapi/funcs/tokens-issue.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await tokensIssue(sdk, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssue failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.ClientCredentialsRequest](../../models/client-credentials-request.md)                                                                                                  | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.TokenData](../../models/token-data.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.OAuth2ErrorResponse | 400, 401                   | application/json           |
| errors.OAuth2ErrorResponse | 502                        | application/json           |
| errors.SDKDefaultError     | 4XX, 5XX                   | \*/\*                      |

## ~~issueFluidTokenLegacy~~

**Deprecated** — prefer `POST /oauth2/token` with `grant_type=client_credentials`.

Validates client credentials against the Authorization Server and generates
a JWT signed by Fluid carrying `workspace_id`, `tenant_id`, `client_id`, and
`credential_type` claims.


> :warning: **DEPRECATED**: This will be removed in a future release, please migrate away from it as soon as possible.

### Example Usage: invalid_request

<!-- UsageSnippet language="typescript" operationID="issueFluidTokenLegacy" method="post" path="/oauth2/token-fluid-legacy" example="invalid_request" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.tokens.issueFluidTokenLegacy({
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
import { SDKCore } from "openapi/core.js";
import { tokensIssueFluidTokenLegacy } from "openapi/funcs/tokens-issue-fluid-token-legacy.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await tokensIssueFluidTokenLegacy(sdk, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueFluidTokenLegacy failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_scope

<!-- UsageSnippet language="typescript" operationID="issueFluidTokenLegacy" method="post" path="/oauth2/token-fluid-legacy" example="invalid_scope" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.tokens.issueFluidTokenLegacy({
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
import { SDKCore } from "openapi/core.js";
import { tokensIssueFluidTokenLegacy } from "openapi/funcs/tokens-issue-fluid-token-legacy.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await tokensIssueFluidTokenLegacy(sdk, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueFluidTokenLegacy failed:", res.error);
  }
}

run();
```
### Example Usage: unsupported_grant_type

<!-- UsageSnippet language="typescript" operationID="issueFluidTokenLegacy" method="post" path="/oauth2/token-fluid-legacy" example="unsupported_grant_type" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const result = await sdk.tokens.issueFluidTokenLegacy({
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
import { SDKCore } from "openapi/core.js";
import { tokensIssueFluidTokenLegacy } from "openapi/funcs/tokens-issue-fluid-token-legacy.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore({
  bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
});

async function run() {
  const res = await tokensIssueFluidTokenLegacy(sdk, {
    grantType: "client_credentials",
    clientId: "fld-cred-acme-corp--api--postman-primary",
    clientSecret: "dGhpcyBpcyBhIHNlY3JldA",
    scope: "fluid:api",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueFluidTokenLegacy failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.ClientCredentialsRequest](../../models/client-credentials-request.md)                                                                                                  | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.TokenData](../../models/token-data.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.OAuth2ErrorResponse | 400, 401                   | application/json           |
| errors.OAuth2ErrorResponse | 502                        | application/json           |
| errors.SDKDefaultError     | 4XX, 5XX                   | \*/\*                      |

## issueUser

Issues a short-lived bootstrap JWT for an end user (workspace or customer scope).

The token lifetime is capped at `BOOTSTRAP_TOKEN_TTL_SECONDS` (default: 300s)
regardless of the `expires_in` value in the request. This token is single-use
and is intended to be exchanged immediately via `POST /users/token/exchange`.

Supported authentication modes:
- `Authorization: Bearer <m2m_token>` — preferred. The token must be a
  Fluid-signed M2M JWT with `scope` including `fluid:api`.
  Canonical first-access provisioning is only available in this mode.
- HTTP Basic Auth with `client_id` + `client_secret`.
  Provisioning is skipped in this mode.

If `customer_external_id` is present, the JWT is issued with `scope: customer`.
Otherwise it is issued with `scope: workspace`.


### Example Usage: email_required

<!-- UsageSnippet language="typescript" operationID="issueUserToken" method="post" path="/users/token" example="email_required" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK();

async function run() {
  const result = await sdk.tokens.issueUser({
    bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
  }, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 300,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SDKCore } from "openapi/core.js";
import { tokensIssueUser } from "openapi/funcs/tokens-issue-user.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore();

async function run() {
  const res = await tokensIssueUser(sdk, {
    bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
  }, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 300,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueUser failed:", res.error);
  }
}

run();
```
### Example Usage: external_id_required

<!-- UsageSnippet language="typescript" operationID="issueUserToken" method="post" path="/users/token" example="external_id_required" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK();

async function run() {
  const result = await sdk.tokens.issueUser({
    bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
  }, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 300,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SDKCore } from "openapi/core.js";
import { tokensIssueUser } from "openapi/funcs/tokens-issue-user.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore();

async function run() {
  const res = await tokensIssueUser(sdk, {
    bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
  }, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 300,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueUser failed:", res.error);
  }
}

run();
```
### Example Usage: invalid_body

<!-- UsageSnippet language="typescript" operationID="issueUserToken" method="post" path="/users/token" example="invalid_body" -->
```typescript
import { SDK } from "openapi";

const sdk = new SDK();

async function run() {
  const result = await sdk.tokens.issueUser({
    bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
  }, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 300,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { SDKCore } from "openapi/core.js";
import { tokensIssueUser } from "openapi/funcs/tokens-issue-user.js";

// Use `SDKCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const sdk = new SDKCore();

async function run() {
  const res = await tokensIssueUser(sdk, {
    bearerAuth: "<YOUR_BEARER_TOKEN_HERE>",
  }, {
    externalId: "user-123",
    customerExternalId: "loja-a",
    email: "alice@acme.com",
    givenName: "Alice",
    familyName: "Smith",
    expiresIn: 300,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("tokensIssueUser failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.UserTokenRequest](../../models/user-token-request.md)                                                                                                                  | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `security`                                                                                                                                                                     | [operations.IssueUserTokenSecurity](../../models/operations/issue-user-token-security.md)                                                                                      | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.UserTokenData](../../models/user-token-data.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.OAuth2ErrorResponse | 400, 401, 403, 404, 409    | application/json           |
| errors.OAuth2ErrorResponse | 502                        | application/json           |
| errors.SDKDefaultError     | 4XX, 5XX                   | \*/\*                      |