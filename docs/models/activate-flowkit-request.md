# ActivateFlowkitRequest

## Example Usage

```typescript
import { ActivateFlowkitRequest } from "fluidapi/models";

let value: ActivateFlowkitRequest = {
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
};
```

## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `credentials`                                                              | [models.FlowkitCredentials](../models/flowkit-credentials.md)              | :heavy_check_mark:                                                         | N/A                                                                        |
| `data`                                                                     | [models.FlowkitActivationContext](../models/flowkit-activation-context.md) | :heavy_check_mark:                                                         | N/A                                                                        |