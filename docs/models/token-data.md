# TokenData

## Example Usage

```typescript
import { TokenData } from "openapi/models";

let value: TokenData = {
  accessToken: "<value>",
  tokenType: "Bearer",
  expiresIn: 3600,
  scope: "fluid:api",
};
```

## Fields

| Field                                                           | Type                                                            | Required                                                        | Description                                                     | Example                                                         |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `accessToken`                                                   | *string*                                                        | :heavy_check_mark:                                              | JWT access token                                                |                                                                 |
| `tokenType`                                                     | [models.TokenDataTokenType](../models/token-data-token-type.md) | :heavy_check_mark:                                              | N/A                                                             | Bearer                                                          |
| `expiresIn`                                                     | *number*                                                        | :heavy_check_mark:                                              | Token lifetime in seconds                                       | 3600                                                            |
| `scope`                                                         | *string*                                                        | :heavy_minus_sign:                                              | Space-separated list of granted scopes                          | fluid:api                                                       |