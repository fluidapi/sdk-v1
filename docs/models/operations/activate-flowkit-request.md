# ActivateFlowkitRequest

## Example Usage

```typescript
import { ActivateFlowkitRequest } from "fluidapi/models/operations";

let value: ActivateFlowkitRequest = {
  tenant: "contaazul",
  integration: "tray",
  key: "dab7e862-5899-4993-b50b-2fe8c4535b8e",
  body: {
    credentials: {
      "url": "https://1225878.commercesuite.com.br",
      "code": "504c234370fd5bc6224ad99e154c039fbecbd9d893...",
    },
    data: {
      identifier: "loja01",
      xTenantId: "3363001",
      xUserId: "58139234",
      xEmail: "user@devportal.com",
    },
  },
};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               | Example                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `tenant`                                                                  | *string*                                                                  | :heavy_check_mark:                                                        | Tenant slug (e.g. `contaazul`).                                           | contaazul                                                                 |
| `integration`                                                             | *string*                                                                  | :heavy_check_mark:                                                        | Integration identifier (e.g. `tray`, `contaazulprivado`).                 | tray                                                                      |
| `key`                                                                     | *string*                                                                  | :heavy_check_mark:                                                        | Flowkit definition key (UUID).                                            | dab7e862-5899-4993-b50b-2fe8c4535b8e                                      |
| `body`                                                                    | [models.ActivateFlowkitRequest](../../models/activate-flowkit-request.md) | :heavy_check_mark:                                                        | N/A                                                                       |                                                                           |