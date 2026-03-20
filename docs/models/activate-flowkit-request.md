# ActivateFlowkitRequest

## Example Usage

```typescript
import { ActivateFlowkitRequest } from "fluidapi/models";

let value: ActivateFlowkitRequest = {
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
};
```

## Fields

| Field                                                                                                      | Type                                                                                                       | Required                                                                                                   | Description                                                                                                | Example                                                                                                    |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `credentials`                                                                                              | Record<string, *any*>                                                                                      | :heavy_check_mark:                                                                                         | Connector-specific authentication credentials.                                                             | {<br/>"url": "https://1225878.commercesuite.com.br",<br/>"code": "504c234370fd5bc6224ad99e154c039fbecbd9d893..."<br/>} |
| `data`                                                                                                     | [models.ActivateFlowkitRequestData](../models/activate-flowkit-request-data.md)                            | :heavy_check_mark:                                                                                         | Per-tenant runtime metadata passed to the flowkit.                                                         |                                                                                                            |