# FlowkitActivatedItem

## Example Usage

```typescript
import { FlowkitActivatedItem } from "fluidapi/models";

let value: FlowkitActivatedItem = {
  typename: "FlowKitActivatedResponse",
  id: "bling-linx-1.0.7",
  flowkitName: "bling-linx",
  flowkitRevision: "1.0.7",
  identifier: "flowkit-test-test",
  status: "success",
  activations: 1,
  flows: 4,
  connectors: [
    "linx-commerce",
    "fluid-flow",
    "storage",
    "http",
  ],
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
};
```

## Fields

| Field                                                                           | Type                                                                            | Required                                                                        | Description                                                                     | Example                                                                         |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `typename`                                                                      | *string*                                                                        | :heavy_minus_sign:                                                              | N/A                                                                             | FlowKitActivatedResponse                                                        |
| `id`                                                                            | *string*                                                                        | :heavy_minus_sign:                                                              | Composite ID — `{flowkit_name}-{revision}`.                                     | bling-linx-1.0.7                                                                |
| `flowkitName`                                                                   | *string*                                                                        | :heavy_minus_sign:                                                              | N/A                                                                             | bling-linx                                                                      |
| `flowkitRevision`                                                               | *string*                                                                        | :heavy_minus_sign:                                                              | N/A                                                                             | 1.0.7                                                                           |
| `identifier`                                                                    | *string*                                                                        | :heavy_minus_sign:                                                              | Per-tenant identifier set at activation time.                                   | flowkit-test-test                                                               |
| `status`                                                                        | [models.FlowkitActivatedItemStatus](../models/flowkit-activated-item-status.md) | :heavy_minus_sign:                                                              | N/A                                                                             | success                                                                         |
| `activations`                                                                   | *number*                                                                        | :heavy_minus_sign:                                                              | N/A                                                                             | 1                                                                               |
| `flows`                                                                         | *number*                                                                        | :heavy_minus_sign:                                                              | N/A                                                                             | 4                                                                               |
| `connectors`                                                                    | *string*[]                                                                      | :heavy_minus_sign:                                                              | N/A                                                                             | [<br/>"linx-commerce",<br/>"fluid-flow",<br/>"storage",<br/>"http"<br/>]        |
| `audit`                                                                         | [models.AuditByName](../models/audit-by-name.md)                                | :heavy_minus_sign:                                                              | N/A                                                                             |                                                                                 |