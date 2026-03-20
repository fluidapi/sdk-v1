# FlowkitUserAuditEntry

## Example Usage

```typescript
import { FlowkitUserAuditEntry } from "fluidapi/models";

let value: FlowkitUserAuditEntry = {
  firstName: "Luigi",
  lastName: "da Silva",
  timestamp: new Date("2026-02-27T14:54:41.103Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `firstName`                                                                                   | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           | Luigi                                                                                         |
| `lastName`                                                                                    | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           | da Silva                                                                                      |
| `timestamp`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | N/A                                                                                           | 2026-02-27T14:54:41.103Z                                                                      |