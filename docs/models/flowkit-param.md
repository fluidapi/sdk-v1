# FlowkitParam

## Example Usage

```typescript
import { FlowkitParam } from "fluidapi/models";

let value: FlowkitParam = {
  key: "descricao_centro_custo",
  description: "Descrição do Centro de Custo",
  type: "string",
  required: true,
};
```

## Fields

| Field                        | Type                         | Required                     | Description                  | Example                      |
| ---------------------------- | ---------------------------- | ---------------------------- | ---------------------------- | ---------------------------- |
| `key`                        | *string*                     | :heavy_check_mark:           | N/A                          | descricao_centro_custo       |
| `description`                | *string*                     | :heavy_minus_sign:           | N/A                          | Descrição do Centro de Custo |
| `type`                       | *string*                     | :heavy_check_mark:           | N/A                          | string                       |
| `required`                   | *boolean*                    | :heavy_check_mark:           | N/A                          | true                         |