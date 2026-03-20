# Key

## Example Usage

```typescript
import { Key } from "openapi/models";

let value: Key = {
  kty: "RSA",
  kid: "fld-iam-rs256-2026-03",
  use: "sig",
  alg: "RS256",
  n: "<value>",
  e: "<value>",
};
```

## Fields

| Field                 | Type                  | Required              | Description           | Example               |
| --------------------- | --------------------- | --------------------- | --------------------- | --------------------- |
| `kty`                 | *string*              | :heavy_check_mark:    | N/A                   | RSA                   |
| `kid`                 | *string*              | :heavy_check_mark:    | N/A                   | fld-iam-rs256-2026-03 |
| `use`                 | *string*              | :heavy_check_mark:    | N/A                   | sig                   |
| `alg`                 | *string*              | :heavy_check_mark:    | N/A                   | RS256                 |
| `n`                   | *string*              | :heavy_check_mark:    | N/A                   |                       |
| `e`                   | *string*              | :heavy_check_mark:    | N/A                   |                       |