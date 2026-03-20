# FlowkitActivationListResponseData

## Example Usage

```typescript
import { FlowkitActivationListResponseData } from "fluidapi/models";

let value: FlowkitActivationListResponseData = {
  data: [
    {
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
    },
  ],
  total: {
    typename: "Meta",
    count: 4,
  },
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `data`                                                               | [models.FlowkitActivatedItem](../models/flowkit-activated-item.md)[] | :heavy_minus_sign:                                                   | N/A                                                                  |
| `total`                                                              | [models.Meta](../models/meta.md)                                     | :heavy_minus_sign:                                                   | N/A                                                                  |