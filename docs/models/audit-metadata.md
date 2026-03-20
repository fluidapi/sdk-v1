# AuditMetadata

## Example Usage

```typescript
import { AuditMetadata } from "fluidapi/models";

let value: AuditMetadata = {
  created: {
    timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
    userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
  },
  updateHistory: [
    {
      timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
      userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
    },
  ],
  updated: {
    timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
    userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
  },
};
```

## Fields

| Field                                           | Type                                            | Required                                        | Description                                     |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| `created`                                       | [models.AuditEntry](../models/audit-entry.md)   | :heavy_check_mark:                              | N/A                                             |
| `updateHistory`                                 | [models.AuditEntry](../models/audit-entry.md)[] | :heavy_check_mark:                              | N/A                                             |
| `updated`                                       | [models.AuditEntry](../models/audit-entry.md)   | :heavy_check_mark:                              | N/A                                             |