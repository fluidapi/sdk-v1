# ActivateFlowkitRequest

## Example Usage

```typescript
import { ActivateFlowkitRequest } from "fluidapi/models/operations";

let value: ActivateFlowkitRequest = {
  key: "dab7e862-5899-4993-b50b-2fe8c4535b8e",
  body: {
    credentials: {
      url: "https://1225878.commercesuite.com.br",
      code: "504c234370fd5bc6224ad99e154c039fbecbd9d893fajsdoi78y87sdysj9sdd",
    },
    data: {
      identifier: "loja01",
      xTenantId: "3363001",
      xUserId: "58139234",
      xEmail: "cliente@devportal.com",
    },
  },
};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               | Example                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `key`                                                                     | *string*                                                                  | :heavy_check_mark:                                                        | Activation key used to authorize the Flowkit activation.                  | dab7e862-5899-4993-b50b-2fe8c4535b8e                                      |
| `body`                                                                    | [models.ActivateFlowkitRequest](../../models/activate-flowkit-request.md) | :heavy_check_mark:                                                        | N/A                                                                       |                                                                           |