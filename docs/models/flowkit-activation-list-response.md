# FlowkitActivationListResponse

## Example Usage

```typescript
import { FlowkitActivationListResponse } from "fluidapi/models";

let value: FlowkitActivationListResponse = {
  data: {
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
  },
};
```

## Fields

| Field                                                                                          | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `data`                                                                                         | [models.FlowkitActivationListResponseData](../models/flowkit-activation-list-response-data.md) | :heavy_minus_sign:                                                                             | N/A                                                                                            |