# AuditById

## Example Usage

```typescript
import { AuditById } from "fluidapi/models";

let value: AuditById = {
  created: {
    timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
    userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
  },
  updated: {
    timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
    userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
  },
  updateHistory: [
    {
      timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
      userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
    },
  ],
};
```

## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `created`                                                 | [models.AuditEntryById](../models/audit-entry-by-id.md)   | :heavy_minus_sign:                                        | Audit entry carrying a user_id (activation response).     |
| `updated`                                                 | [models.AuditEntryById](../models/audit-entry-by-id.md)   | :heavy_minus_sign:                                        | Audit entry carrying a user_id (activation response).     |
| `updateHistory`                                           | [models.AuditEntryById](../models/audit-entry-by-id.md)[] | :heavy_minus_sign:                                        | N/A                                                       |