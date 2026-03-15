# IssueTokenResponse

Access token issued

## Example Usage

```typescript
import { IssueTokenResponse } from "fluidapi/models/operations";

let value: IssueTokenResponse = {
  ok: true,
  data: {
    accessToken: "<value>",
    tokenType: "bearer",
    expiresIn: 3600,
    scope: "fluid:api",
  },
};
```

## Fields

| Field                                          | Type                                           | Required                                       | Description                                    | Example                                        |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `ok`                                           | *boolean*                                      | :heavy_check_mark:                             | N/A                                            | true                                           |
| `data`                                         | [models.TokenData](../../models/token-data.md) | :heavy_minus_sign:                             | N/A                                            |                                                |