# FlowkitListResponseData

## Example Usage

```typescript
import { FlowkitListResponseData } from "fluidapi/models";

let value: FlowkitListResponseData = {
  data: [
    {
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
    },
  ],
  total: {
    typename: "Meta",
    count: 4,
  },
};
```

## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `data`                                                        | [models.FlowkitDefinition](../models/flowkit-definition.md)[] | :heavy_minus_sign:                                            | N/A                                                           |
| `total`                                                       | [models.Meta](../models/meta.md)                              | :heavy_minus_sign:                                            | N/A                                                           |