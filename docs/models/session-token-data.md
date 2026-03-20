# SessionTokenData

## Example Usage

```typescript
import { SessionTokenData } from "openapi/models";

let value: SessionTokenData = {
  accessToken: "<value>",
  tokenType: "bearer",
  expiresIn: 3600,
};
```

## Fields

| Field                                                                          | Type                                                                           | Required                                                                       | Description                                                                    | Example                                                                        |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `accessToken`                                                                  | *string*                                                                       | :heavy_check_mark:                                                             | Hydra-issued access token                                                      |                                                                                |
| `refreshToken`                                                                 | *string*                                                                       | :heavy_minus_sign:                                                             | Hydra refresh token; use with `POST /users/token/refresh`                      |                                                                                |
| `tokenType`                                                                    | [models.SessionTokenDataTokenType](../models/session-token-data-token-type.md) | :heavy_check_mark:                                                             | N/A                                                                            | bearer                                                                         |
| `expiresIn`                                                                    | *number*                                                                       | :heavy_check_mark:                                                             | Access token lifetime in seconds                                               | 3600                                                                           |