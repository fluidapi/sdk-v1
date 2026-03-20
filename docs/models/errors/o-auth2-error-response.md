# OAuth2ErrorResponse

Invalid request parameters

## Example Usage

```typescript
import { OAuth2ErrorResponse } from "openapi/models/errors";

// No examples available for this model
```

## Fields

| Field                            | Type                             | Required                         | Description                      | Example                          |
| -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- |
| `error`                          | *string*                         | :heavy_check_mark:               | OAuth2 error code (RFC 6749)     | invalid_client                   |
| `errorDescription`               | *string*                         | :heavy_minus_sign:               | Human-readable error description | invalid client credentials       |