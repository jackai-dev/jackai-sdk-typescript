# omniwrap-typescript-sdk-mcp

Zero-dependency Node.js MCP JSON-RPC 2.0 stdio server (`2025-11-25` / `2025-06-18`) for **JackAI Platform OS Hub API (public subset)**.

- Schema: `omniwrap.typescript-sdk-mcp/v1`
- Contract SHA-256: `c7ca5e5ebb4c092910ec72b371e188303358c5e34d2908c0a88f782a241162cf`
- Tool surface: `search_docs, list_api_endpoints, get_api_endpoint_schema, execute`

## Security and Isolation

- `OMNIWRAP_MCP_ALLOWED_OPERATIONS`: comma-separated operation allowlist.
- `OMNIWRAP_MCP_READ_ONLY`: set to `1` to block non-read-only operations.
- `OMNIWRAP_MCP_BASE_URL` and authentication tokens stay inside the parent host transport closure. Snippets execute inside a dedicated short-lived Node `worker_threads` V8 isolate with an empty environment (`env: {}`), heap ceilings, and hard wall-clock termination (`worker.terminate()`). Layer OS container or process sandboxing around the server when running untrusted code.

## Operations (8)

- `failUsageQuota` (`POST /v1/kernel/usage/fail`) -> `client.kernel.failUsageQuota`
- `finalizeUsageQuota` (`POST /v1/kernel/usage/finalize`) -> `client.kernel.finalizeUsageQuota`
- `getCurrentUser` (`GET /user/me`) -> `client.user.getCurrentUser`
- `getHealth` (`GET /health`) -> `client.health.getHealth`
- `getSignupPolicy` (`GET /user/auth/signup-policy`) -> `client.user.getSignupPolicy`
- `loginUser` (`POST /user/auth/login`) -> `client.user.loginUser`
- `reserveUsageQuota` (`POST /v1/kernel/usage/reserve`) -> `client.kernel.reserveUsageQuota`
- `submitWaitlistRequest` (`POST /user/auth/waitlist`) -> `client.user.submitWaitlistRequest`
