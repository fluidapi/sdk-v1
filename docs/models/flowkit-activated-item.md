# FlowkitActivatedItem

## Example Usage

```typescript
import { FlowkitActivatedItem } from "fluidapi/models";

let value: FlowkitActivatedItem = {
  typename: "FlowKitActivatedResponse",
  activations: 1,
  audit: {
    created: {
      firstName: "Luigi",
      lastName: "da Silva",
      timestamp: new Date("2026-02-27T14:54:41.103Z"),
    },
    updated: {
      firstName: "Luigi",
      lastName: "da Silva",
      timestamp: new Date("2026-02-27T14:54:41.103Z"),
    },
  },
  connectors: [
    "<value 1>",
    "<value 2>",
    "<value 3>",
  ],
  flowkitName: "bling-linx",
  flowkitRevision: "1.0.7",
  flows: 4,
  id: "bling-linx-1.0.7",
  identifier: "flowkit-test-test",
  status: "success",
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                | Example                                                    |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `typename`                                                 | *string*                                                   | :heavy_check_mark:                                         | N/A                                                        | FlowKitActivatedResponse                                   |
| `activations`                                              | *number*                                                   | :heavy_check_mark:                                         | N/A                                                        | 1                                                          |
| `audit`                                                    | [models.FlowkitUserAudit](../models/flowkit-user-audit.md) | :heavy_check_mark:                                         | N/A                                                        |                                                            |
| `connectors`                                               | *string*[]                                                 | :heavy_check_mark:                                         | N/A                                                        |                                                            |
| `flowkitName`                                              | *string*                                                   | :heavy_check_mark:                                         | N/A                                                        | bling-linx                                                 |
| `flowkitRevision`                                          | *string*                                                   | :heavy_check_mark:                                         | N/A                                                        | 1.0.7                                                      |
| `flows`                                                    | *number*                                                   | :heavy_check_mark:                                         | N/A                                                        | 4                                                          |
| `id`                                                       | *string*                                                   | :heavy_check_mark:                                         | N/A                                                        | bling-linx-1.0.7                                           |
| `identifier`                                               | *string*                                                   | :heavy_check_mark:                                         | N/A                                                        | flowkit-test-test                                          |
| `status`                                                   | *string*                                                   | :heavy_check_mark:                                         | N/A                                                        | success                                                    |