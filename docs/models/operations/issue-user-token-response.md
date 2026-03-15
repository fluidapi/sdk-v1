# IssueUserTokenResponse

User token issued

## Example Usage

```typescript
import { IssueUserTokenResponse } from "fluidapi/models/operations";

let value: IssueUserTokenResponse = {
  ok: true,
  data: {
    accessToken: "<value>",
    tokenType: "Bearer",
    expiresIn: 3600,
  },
};
```

## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             | Example                                                 |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `ok`                                                    | *boolean*                                               | :heavy_check_mark:                                      | N/A                                                     | true                                                    |
| `data`                                                  | [models.UserTokenData](../../models/user-token-data.md) | :heavy_minus_sign:                                      | N/A                                                     |                                                         |