# FlowkitDefinition

## Example Usage

```typescript
import { FlowkitDefinition } from "fluidapi/models";

let value: FlowkitDefinition = {
  typename: "FlowKit",
  id: "conta-azul-flexy-1.0.0",
  name: "conta-azul-flexy",
  title: "Conta Azul-Flexy",
  revision: "1.0.0",
  tenantId: "fluid-31de26d847544df9b3259dff43c99f00",
  connectors: [
    {
      connectorId: "64be93a5a1fb031f8ec62a39",
      connectorSlug: "conta-azul",
    },
  ],
  flows: [
    {
      flowRevision: 0,
    },
  ],
  params: [
    {
      key: "descricao_centro_custo",
      description: "Descrição do Centro de Custo",
      type: "string",
      required: true,
    },
  ],
  audit: {
    updated: {
      firstName: "Luigi",
      lastName: "da Silva",
      timestamp: new Date("2026-02-27T14:54:41.103Z"),
    },
  },
};
```

## Fields

| Field                                                              | Type                                                               | Required                                                           | Description                                                        | Example                                                            |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `typename`                                                         | *string*                                                           | :heavy_minus_sign:                                                 | N/A                                                                | FlowKit                                                            |
| `id`                                                               | *string*                                                           | :heavy_minus_sign:                                                 | N/A                                                                | conta-azul-flexy-1.0.0                                             |
| `name`                                                             | *string*                                                           | :heavy_minus_sign:                                                 | N/A                                                                | conta-azul-flexy                                                   |
| `title`                                                            | *string*                                                           | :heavy_minus_sign:                                                 | N/A                                                                | Conta Azul-Flexy                                                   |
| `revision`                                                         | *string*                                                           | :heavy_minus_sign:                                                 | N/A                                                                | 1.0.0                                                              |
| `description`                                                      | *string*                                                           | :heavy_minus_sign:                                                 | N/A                                                                |                                                                    |
| `tenantId`                                                         | *string*                                                           | :heavy_minus_sign:                                                 | N/A                                                                | fluid-31de26d847544df9b3259dff43c99f00                             |
| `connectors`                                                       | [models.FlowkitConnectorRef](../models/flowkit-connector-ref.md)[] | :heavy_minus_sign:                                                 | N/A                                                                |                                                                    |
| `flows`                                                            | [models.FlowkitFlowRef](../models/flowkit-flow-ref.md)[]           | :heavy_minus_sign:                                                 | N/A                                                                |                                                                    |
| `params`                                                           | [models.FlowkitParam](../models/flowkit-param.md)[]                | :heavy_minus_sign:                                                 | N/A                                                                |                                                                    |
| `audit`                                                            | [models.Audit](../models/audit.md)                                 | :heavy_minus_sign:                                                 | N/A                                                                |                                                                    |