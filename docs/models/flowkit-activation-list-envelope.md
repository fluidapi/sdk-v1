# FlowkitActivationListEnvelope

## Example Usage

```typescript
import { FlowkitActivationListEnvelope } from "fluidapi/models";

let value: FlowkitActivationListEnvelope = {
  data: [
    {
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
      ],
      flowkitName: "bling-linx",
      flowkitRevision: "1.0.7",
      flows: 4,
      id: "bling-linx-1.0.7",
      identifier: "flowkit-test-test",
      status: "success",
    },
  ],
  total: {
    typename: "Meta",
    count: 13,
  },
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `data`                                                               | [models.FlowkitActivatedItem](../models/flowkit-activated-item.md)[] | :heavy_check_mark:                                                   | N/A                                                                  |
| `total`                                                              | [models.MetaCount](../models/meta-count.md)                          | :heavy_check_mark:                                                   | N/A                                                                  |