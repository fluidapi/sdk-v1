# AuditEntryByName

Audit entry carrying first_name / last_name (list responses).

## Example Usage

```typescript
import { AuditEntryByName } from "fluidapi/models";

let value: AuditEntryByName = {
  firstName: "Luigi",
  lastName: "da Silva",
  timestamp: new Date("2026-02-27T14:54:41.103Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `firstName`                                                                                   | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           | Luigi                                                                                         |
| `lastName`                                                                                    | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           | da Silva                                                                                      |
| `timestamp`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           | 2026-02-27T14:54:41.103Z                                                                      |