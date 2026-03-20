# FlowkitUserAudit

## Example Usage

```typescript
import { FlowkitUserAudit } from "fluidapi/models";

let value: FlowkitUserAudit = {
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
};
```

## Fields

| Field                                                                 | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `created`                                                             | [models.FlowkitUserAuditEntry](../models/flowkit-user-audit-entry.md) | :heavy_check_mark:                                                    | N/A                                                                   |
| `updated`                                                             | [models.FlowkitUserAuditEntry](../models/flowkit-user-audit-entry.md) | :heavy_check_mark:                                                    | N/A                                                                   |