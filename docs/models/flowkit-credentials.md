# FlowkitCredentials

## Example Usage

```typescript
import { FlowkitCredentials } from "fluidapi/models";

let value: FlowkitCredentials = {
  url: "https://1225878.commercesuite.com.br",
  code: "504c234370fd5bc6224ad99e154c039fbecbd9d893fajsdoi78y87sdysj9sdd",
};
```

## Fields

| Field                                                           | Type                                                            | Required                                                        | Description                                                     | Example                                                         |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `url`                                                           | *string*                                                        | :heavy_check_mark:                                              | Base URL for the connected commerce platform.                   | https://1225878.commercesuite.com.br                            |
| `code`                                                          | *string*                                                        | :heavy_check_mark:                                              | Integration credential code/token.                              | 504c234370fd5bc6224ad99e154c039fbecbd9d893fajsdoi78y87sdysj9sdd |