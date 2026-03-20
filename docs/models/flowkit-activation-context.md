# FlowkitActivationContext

## Example Usage

```typescript
import { FlowkitActivationContext } from "fluidapi/models";

let value: FlowkitActivationContext = {
  identifier: "loja01",
  xTenantId: "3363001",
  xUserId: "58139234",
  xEmail: "cliente@devportal.com",
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              | Example                                                  |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `identifier`                                             | *string*                                                 | :heavy_check_mark:                                       | Client-side identifier for the activated Flowkit.        | loja01                                                   |
| `xTenantId`                                              | *string*                                                 | :heavy_check_mark:                                       | Tenant identifier propagated to the integration context. | 3363001                                                  |
| `xUserId`                                                | *string*                                                 | :heavy_check_mark:                                       | User identifier propagated to the integration context.   | 58139234                                                 |
| `xEmail`                                                 | *string*                                                 | :heavy_check_mark:                                       | User email propagated to the integration context.        | cliente@devportal.com                                    |