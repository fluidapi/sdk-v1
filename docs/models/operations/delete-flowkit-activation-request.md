# DeleteFlowkitActivationRequest

## Example Usage

```typescript
import { DeleteFlowkitActivationRequest } from "fluidapi/models/operations";

let value: DeleteFlowkitActivationRequest = {
  tenant: "contaazul",
  id: "bling-linx-1.0.7",
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        | Example                                            |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `tenant`                                           | *string*                                           | :heavy_check_mark:                                 | Tenant slug (e.g. `contaazul`).                    | contaazul                                          |
| `id`                                               | *string*                                           | :heavy_check_mark:                                 | Activation ID to delete (e.g. `bling-linx-1.0.7`). | bling-linx-1.0.7                                   |