# ErrorT

## Example Usage

```typescript
import { ErrorT } from "fluidapi/models";

let value: ErrorT = {
  code: "<value>",
  message: "<value>",
};
```

## Fields

| Field                       | Type                        | Required                    | Description                 |
| --------------------------- | --------------------------- | --------------------------- | --------------------------- |
| `code`                      | *string*                    | :heavy_check_mark:          | Machine-readable error code |
| `message`                   | *string*                    | :heavy_check_mark:          | Human-readable description  |