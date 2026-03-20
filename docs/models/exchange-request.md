# ExchangeRequest

## Example Usage

```typescript
import { ExchangeRequest } from "openapi/models";

let value: ExchangeRequest = {
  token: "eyJhbGciOiJSUzI1NiIsImtpZCI6Ik9UO...",
};
```

## Fields

| Field                                       | Type                                        | Required                                    | Description                                 | Example                                     |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| `token`                                     | *string*                                    | :heavy_check_mark:                          | Bootstrap JWT issued by `POST /users/token` | eyJhbGciOiJSUzI1NiIsImtpZCI6Ik9UO...        |