# AuditByName

## Example Usage

```typescript
import { AuditByName } from "fluidapi/models";

let value: AuditByName = {
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

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `created`                                                     | [models.AuditEntryByName](../models/audit-entry-by-name.md)   | :heavy_minus_sign:                                            | Audit entry carrying first_name / last_name (list responses). |
| `updated`                                                     | [models.AuditEntryByName](../models/audit-entry-by-name.md)   | :heavy_minus_sign:                                            | Audit entry carrying first_name / last_name (list responses). |