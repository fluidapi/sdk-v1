# Audit

## Example Usage

```typescript
import { Audit } from "fluidapi/models";

let value: Audit = {
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
| `updated`                                                     | [models.AuditEntryByName](../models/audit-entry-by-name.md)   | :heavy_minus_sign:                                            | Audit entry carrying first_name / last_name (list responses). |