# RefreshRequest

## Example Usage

```typescript
import { RefreshRequest } from "fluidapi/models";

let value: RefreshRequest = {
  refreshToken: "ory_rt_...",
};
```

## Fields

| Field                                                                                       | Type                                                                                        | Required                                                                                    | Description                                                                                 | Example                                                                                     |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `refreshToken`                                                                              | *string*                                                                                    | :heavy_check_mark:                                                                          | Hydra refresh token obtained from `/users/token/exchange` or a prior `/users/token/refresh` | ory_rt_...                                                                                  |