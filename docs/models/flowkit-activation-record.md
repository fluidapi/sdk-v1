# FlowkitActivationRecord

Activation record returned after a successful POST activate.

## Example Usage

```typescript
import { FlowkitActivationRecord } from "fluidapi/models";

let value: FlowkitActivationRecord = {
  id: "9074bd4d-23e0-11f1-b769-4e4d4c5f610c",
  flowkitName: "conta-azul-tray-2",
  flowkitRevision: "1.0.0",
  description: "descricao do flowkit",
  identifier: "loja06",
  published: true,
  status: "in_progress",
  connectors: [
    "contaazulprivado",
    "tray",
  ],
  audit: {
    created: {
      timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
      userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
    },
    updated: {
      timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
      userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
    },
    updateHistory: [
      {
        timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
        userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
      },
    ],
  },
};
```

## Fields

| Field                                                                                 | Type                                                                                  | Required                                                                              | Description                                                                           | Example                                                                               |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `id`                                                                                  | *string*                                                                              | :heavy_minus_sign:                                                                    | N/A                                                                                   | 9074bd4d-23e0-11f1-b769-4e4d4c5f610c                                                  |
| `flowkitName`                                                                         | *string*                                                                              | :heavy_minus_sign:                                                                    | N/A                                                                                   | conta-azul-tray-2                                                                     |
| `flowkitRevision`                                                                     | *string*                                                                              | :heavy_minus_sign:                                                                    | N/A                                                                                   | 1.0.0                                                                                 |
| `description`                                                                         | *string*                                                                              | :heavy_minus_sign:                                                                    | N/A                                                                                   | descricao do flowkit                                                                  |
| `identifier`                                                                          | *string*                                                                              | :heavy_minus_sign:                                                                    | N/A                                                                                   | loja06                                                                                |
| `published`                                                                           | *boolean*                                                                             | :heavy_minus_sign:                                                                    | N/A                                                                                   | true                                                                                  |
| `status`                                                                              | [models.FlowkitActivationRecordStatus](../models/flowkit-activation-record-status.md) | :heavy_minus_sign:                                                                    | N/A                                                                                   | in_progress                                                                           |
| `connectors`                                                                          | *string*[]                                                                            | :heavy_minus_sign:                                                                    | N/A                                                                                   | [<br/>"contaazulprivado",<br/>"tray"<br/>]                                            |
| `audit`                                                                               | [models.AuditById](../models/audit-by-id.md)                                          | :heavy_minus_sign:                                                                    | N/A                                                                                   |                                                                                       |