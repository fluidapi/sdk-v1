# UserTokenData

## Example Usage

```typescript
import { UserTokenData } from "fluidapi/models";

let value: UserTokenData = {
  accessToken: "<value>",
  tokenType: "Bearer",
  expiresIn: 3600,
};
```

## Fields

| Field              | Type               | Required           | Description        | Example            |
| ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
| `accessToken`      | *string*           | :heavy_check_mark: | N/A                |                    |
| `tokenType`        | *string*           | :heavy_check_mark: | N/A                | Bearer             |
| `expiresIn`        | *number*           | :heavy_minus_sign: | N/A                | 3600               |