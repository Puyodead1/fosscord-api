# Spacebar API Types

This package contains typings for objects in the Spacebar API and a fully typed API request builder.

### Example Usage

If you just need access to types:

```typescript
import type { User } from "spacebar-types";
```

If you want to send requests:

```typescript
import { API } from "spacebar-types";

// Initialise a new API client:
const client = new API();

// or with authentication:
const client = new API({ authentication: { bearer: "token" } });

// Make requests with ease:
client
    .get("/users/@me")
    // Fully typed responses!
    .then((user) => user.username);

// No need to worry about the details:
let channel_id = "some channel id";
client.post(`/channels/${channel_id}/messages`, {
    // Parameters given are fully typed as well!
    content: "some content",
});
```

For more details on how this works, see the [README of @insertish/oapi](https://github.com/insertish/oapi#example).
