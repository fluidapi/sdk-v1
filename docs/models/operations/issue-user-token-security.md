# IssueUserTokenSecurity

## Example Usage

```typescript
import { IssueUserTokenSecurity } from "fluidapi/models/operations";

let value: IssueUserTokenSecurity = {
  basicAuth: {
    username: "",
    password: "",
  },
};
```

## Fields

| Field                                                       | Type                                                        | Required                                                    | Description                                                 |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| `bearerAuth`                                                | *string*                                                    | :heavy_minus_sign:                                          | N/A                                                         |
| `basicAuth`                                                 | [models.SchemeBasicAuth](../../models/scheme-basic-auth.md) | :heavy_minus_sign:                                          | N/A                                                         |