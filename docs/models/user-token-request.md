# UserTokenRequest

## Example Usage

```typescript
import { UserTokenRequest } from "fluidapi/models";

let value: UserTokenRequest = {
  externalId: "user-123",
  customerExternalId: "loja-a",
  email: "alice@acme.com",
  givenName: "Alice",
  familyName: "Smith",
  expiresIn: 3600,
};
```

## Fields

| Field                               | Type                                | Required                            | Description                         | Example                             |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `externalId`                        | *string*                            | :heavy_check_mark:                  | N/A                                 | user-123                            |
| `customerExternalId`                | *string*                            | :heavy_minus_sign:                  | N/A                                 | loja-a                              |
| `email`                             | *string*                            | :heavy_minus_sign:                  | N/A                                 | alice@acme.com                      |
| `givenName`                         | *string*                            | :heavy_minus_sign:                  | N/A                                 | Alice                               |
| `familyName`                        | *string*                            | :heavy_minus_sign:                  | N/A                                 | Smith                               |
| `expiresIn`                         | *number*                            | :heavy_minus_sign:                  | Optional token lifetime in seconds. | 3600                                |