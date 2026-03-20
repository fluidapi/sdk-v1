# FlowkitActivation

## Example Usage

```typescript
import { FlowkitActivation } from "fluidapi/models";

let value: FlowkitActivation = {
  audit: {
    created: {
      timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
      userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
    },
    updateHistory: [
      {
        timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
        userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
      },
    ],
    updated: {
      timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
      userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
    },
  },
  connectors: [
    "contaazulprivado",
    "tray",
  ],
  description: "descricao do flowkit",
  flowkitName: "conta-azul-tray-2",
  flowkitRevision: "1.0.0",
  id: "9074bd4d-23e0-11f1-b769-4e4d4c5f610c",
  identifier: "loja06",
  published: true,
  status: "in_progress",
};
```

## Fields

| Field                                               | Type                                                | Required                                            | Description                                         | Example                                             |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| `audit`                                             | [models.AuditMetadata](../models/audit-metadata.md) | :heavy_check_mark:                                  | N/A                                                 |                                                     |
| `connectors`                                        | *string*[]                                          | :heavy_check_mark:                                  | N/A                                                 | [<br/>"contaazulprivado",<br/>"tray"<br/>]          |
| `description`                                       | *string*                                            | :heavy_check_mark:                                  | N/A                                                 | descricao do flowkit                                |
| `flowkitName`                                       | *string*                                            | :heavy_check_mark:                                  | N/A                                                 | conta-azul-tray-2                                   |
| `flowkitRevision`                                   | *string*                                            | :heavy_check_mark:                                  | N/A                                                 | 1.0.0                                               |
| `id`                                                | *string*                                            | :heavy_check_mark:                                  | N/A                                                 | 9074bd4d-23e0-11f1-b769-4e4d4c5f610c                |
| `identifier`                                        | *string*                                            | :heavy_check_mark:                                  | N/A                                                 | loja06                                              |
| `published`                                         | *boolean*                                           | :heavy_check_mark:                                  | N/A                                                 | true                                                |
| `status`                                            | *string*                                            | :heavy_check_mark:                                  | N/A                                                 | in_progress                                         |