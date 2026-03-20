# AuditEntryById

Audit entry carrying a user_id (activation response).

## Example Usage

```typescript
import { AuditEntryById } from "fluidapi/models";

let value: AuditEntryById = {
  timestamp: new Date("2026-03-19T19:11:22.841037415-03:00"),
  userId: "bc32c03a-e885-4641-aaac-ca9358703d07",
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `timestamp`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           | 2026-03-19T19:11:22.841037415-03:00                                                           |
| `userId`                                                                                      | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           | bc32c03a-e885-4641-aaac-ca9358703d07                                                          |