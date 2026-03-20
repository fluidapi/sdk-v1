# UserTokenData

## Example Usage

```typescript
import { UserTokenData } from "openapi/models";

let value: UserTokenData = {
  accessToken: "<value>",
  tokenType: "Bearer",
  expiresIn: 300,
};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               | Example                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `accessToken`                                                             | *string*                                                                  | :heavy_check_mark:                                                        | N/A                                                                       |                                                                           |
| `tokenType`                                                               | [models.UserTokenDataTokenType](../models/user-token-data-token-type.md)  | :heavy_check_mark:                                                        | N/A                                                                       | Bearer                                                                    |
| `expiresIn`                                                               | *number*                                                                  | :heavy_check_mark:                                                        | Effective token lifetime in seconds (always set; capped at server config) | 300                                                                       |