# ActivateFlowkitRequestData

Per-tenant runtime metadata passed to the flowkit.

## Example Usage

```typescript
import { ActivateFlowkitRequestData } from "fluidapi/models";

let value: ActivateFlowkitRequestData = {
  identifier: "loja01",
  xTenantId: "3363001",
  xUserId: "58139234",
  xEmail: "user@devportal.com",
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              | Example                                                  |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `identifier`                                             | *string*                                                 | :heavy_minus_sign:                                       | Unique identifier for this activation within the tenant. | loja01                                                   |
| `xTenantId`                                              | *string*                                                 | :heavy_minus_sign:                                       | N/A                                                      | 3363001                                                  |
| `xUserId`                                                | *string*                                                 | :heavy_minus_sign:                                       | N/A                                                      | 58139234                                                 |
| `xEmail`                                                 | *string*                                                 | :heavy_minus_sign:                                       | N/A                                                      | user@devportal.com                                       |
| `additionalProperties`                                   | Record<string, *any*>                                    | :heavy_minus_sign:                                       | N/A                                                      |                                                          |