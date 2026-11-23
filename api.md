# JackAI Platform OS Hub API (public subset) TypeScript API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6ImM3Y2E1ZTVlYmI0YzA5MjkxMGVjNzJiMzcxZTE4ODMwMzM1OGM1ZTM0ZDI5MDhjMGE4OGY3ODJhMjQxMTYyY2YiLCJvcGVyYXRpb25fY291bnQiOjgsInJlbmRlcmVyIjoidHlwZXNjcmlwdCIsInZlcnNpb24iOiIxLjUuMCJ9 -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `c7ca5e5ebb4c092910ec72b371e188303358c5e34d2908c0a88f782a241162cf`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **verified**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Client hooks and tracing

`new Client({ hooks })` registers four callbacks. Every attempt starts with `beforeRequest` and ends with exactly one of `onRetry` (another attempt follows), `afterResponse` (the success the call returns) or `onError` (the failure the call reports). Each receives the operation id, the HTTP method, the URL, the request headers, the attempt number (from 1), the time elapsed since the call started and, once the server answered, the HTTP status. No context carries a credential: `Authorization`, `Proxy-Authorization`, `Cookie`, every API-key header and API-key query parameter, and any configured credential value read `[redacted]`. `beforeRequest` is the one hook that may change the request (the documented per-request credential contract, which also reads credentials masked); the other three receive frozen `HookContext` copies.

`new Client({ tracer })` opens one span per call through the tracer interface this SDK defines, named after the operation id, with `http.request.method`, `http.response.status_code` and `http.request.resend_count`. It needs no tracing library; README.md maps it onto the OpenTelemetry API.

## Resource `health`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJoZWFsdGguZ2V0IiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0SGVhbHRoIiwicGF0aCI6Ii9oZWFsdGgiLCJyZXNvdXJjZSI6ImhlYWx0aCIsInNlY3Rpb25fc2hhMjU2IjoiMjQ3YTdiMjA2ZWVjNTViNGQ4MTU1N2JmYTUyMDBiYzVkMDU3OWFhYjg3ZTdjNzRmNWI5ZTA3ZjliNDM3NWMyNiIsInNpZ25hdHVyZV9zaGEyNTYiOiJlYTliN2Q3YTJjYzBlYWMzMjkyYWFkZjQwODRmZDY5ODg4N2E3NjFkZDEzMmZhYTI2OWJhZDlhNzgxYmExY2M4In0 -->
### `client.health.get`

Operation ID: `getHealth`  
Route: `GET` `/health`  
Equivalent member: `client.getHealth`  

#### Signature

```typescript
client.health.get<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Hub liveness status | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.health.get();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgifQ -->

## Resource `kernel`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJrZXJuZWwuZmFpbFVzYWdlUXVvdGEiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiZmFpbFVzYWdlUXVvdGEiLCJwYXRoIjoiL3YxL2tlcm5lbC91c2FnZS9mYWlsIiwicmVzb3VyY2UiOiJrZXJuZWwiLCJzZWN0aW9uX3NoYTI1NiI6IjVmMDMzNjA3ZGIzOTg2MGE2MWZiMTAxOGM4NDgzNTI0YmYwMDZkYTI5NjFhMTUxZWJlNDk5OTg2MGU2MzM2NTMiLCJzaWduYXR1cmVfc2hhMjU2IjoiZWY3YzJhOWQ1MGVhZTJhNTFlMTkwNGYxMDA5ZGZhNjA4YjEzY2YzYjA5MzI3OGYzMzg4YzdhNDAwMzBmYzNmMiJ9 -->
### `client.kernel.failUsageQuota`

Operation ID: `failUsageQuota`  
Route: `POST` `/v1/kernel/usage/fail`  
Equivalent member: `client.failUsageQuota`  

#### Signature

```typescript
client.kernel.failUsageQuota<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation released | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.kernel.failUsageQuota();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmYWlsVXNhZ2VRdW90YSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJrZXJuZWwuZmluYWxpemVVc2FnZVF1b3RhIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImZpbmFsaXplVXNhZ2VRdW90YSIsInBhdGgiOiIvdjEva2VybmVsL3VzYWdlL2ZpbmFsaXplIiwicmVzb3VyY2UiOiJrZXJuZWwiLCJzZWN0aW9uX3NoYTI1NiI6IjgwN2M5NWFiNGZiZjQ2MGNjYjE4MGNiNWJlNDUyYjBlNmNmODQ0NjJjNzBjYjc4YmIzYmYxNjFjZTlmYzI2MmQiLCJzaWduYXR1cmVfc2hhMjU2IjoiZTk5MzVkMTNhZGY2MDAwNDg0ZTA3ZTJjOGU3ZDdlODM1OGI2ZWEyZjEzZTVlYzk4YWRkZDExMDM5NjkzOTIyNiJ9 -->
### `client.kernel.finalizeUsageQuota`

Operation ID: `finalizeUsageQuota`  
Route: `POST` `/v1/kernel/usage/finalize`  
Equivalent member: `client.finalizeUsageQuota`  

#### Signature

```typescript
client.kernel.finalizeUsageQuota<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation finalized | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.kernel.finalizeUsageQuota();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmaW5hbGl6ZVVzYWdlUXVvdGEifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJrZXJuZWwucmVzZXJ2ZVVzYWdlUXVvdGEiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoicmVzZXJ2ZVVzYWdlUXVvdGEiLCJwYXRoIjoiL3YxL2tlcm5lbC91c2FnZS9yZXNlcnZlIiwicmVzb3VyY2UiOiJrZXJuZWwiLCJzZWN0aW9uX3NoYTI1NiI6IjFjYTA1ODk3ODMxZTFmNDE1OGNlZDJlZTQxYTQ2NDBmY2U2Y2U5NWY2ZWJmZDk5YmYxNjEzZTkwNzQ1MzNkMmIiLCJzaWduYXR1cmVfc2hhMjU2IjoiZjE5NzYzN2RlYTNhNzU1ZDhhZDA2ZmM1MzlmYTY0MzdmNGM2OWFmYzdmODYzOTVlYTc1Yzk5MmU5YmI2YzNkYyJ9 -->
### `client.kernel.reserveUsageQuota`

Operation ID: `reserveUsageQuota`  
Route: `POST` `/v1/kernel/usage/reserve`  
Equivalent member: `client.reserveUsageQuota`  

#### Signature

```typescript
client.kernel.reserveUsageQuota<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation lease created | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.kernel.reserveUsageQuota();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZXNlcnZlVXNhZ2VRdW90YSJ9 -->

## Resource `user`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLmdldEN1cnJlbnQiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRDdXJyZW50VXNlciIsInBhdGgiOiIvdXNlci9tZSIsInJlc291cmNlIjoidXNlciIsInNlY3Rpb25fc2hhMjU2IjoiNzBhNjhjZGRkOGU3ZTAxNWNkNjU5YjM0MTBmMDkzNjAxZmE0YjE5Y2EzMjNhYWY4MjhkNzBlOGJiNmJhMGRiYyIsInNpZ25hdHVyZV9zaGEyNTYiOiJhYmNlNjk4NWViMzM2NDViOWVmYWZmNTFlM2YwZjczNTBjYmU1OTIwZmRhMDRiYzhkZWIwYWVmM2U4NGI0MmNjIn0 -->
### `client.user.getCurrent`

Operation ID: `getCurrentUser`  
Route: `GET` `/user/me`  
Equivalent member: `client.getCurrentUser`  

#### Signature

```typescript
client.user.getCurrent<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Current user context | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.user.getCurrent();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRDdXJyZW50VXNlciJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLmdldFNpZ251cFBvbGljeSIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFNpZ251cFBvbGljeSIsInBhdGgiOiIvdXNlci9hdXRoL3NpZ251cC1wb2xpY3kiLCJyZXNvdXJjZSI6InVzZXIiLCJzZWN0aW9uX3NoYTI1NiI6IjhkNWYwYmRjZTU0MWFmMWRhMDBkYTU1MWVjNzY4NTg4Yjg5MzUzOTk1MTVkZWM0NGFkMThiY2ZjNzYwMTU4ZmIiLCJzaWduYXR1cmVfc2hhMjU2IjoiZjgxOWY0ZDJmOWNhOGIxMTA3ZjY4Y2VkOTFlZDdmNjg4NjAzZjRmZTI0ZDhmZmY3NzY5YzZlZGM2YTcxMjZhNiJ9 -->
### `client.user.getSignupPolicy`

Operation ID: `getSignupPolicy`  
Route: `GET` `/user/auth/signup-policy`  
Equivalent member: `client.getSignupPolicy`  

#### Signature

```typescript
client.user.getSignupPolicy<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Current signup policy | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.user.getSignupPolicy();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRTaWdudXBQb2xpY3kifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLmxvZ2luIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImxvZ2luVXNlciIsInBhdGgiOiIvdXNlci9hdXRoL2xvZ2luIiwicmVzb3VyY2UiOiJ1c2VyIiwic2VjdGlvbl9zaGEyNTYiOiIyOWU3NjczYWRlNGY1ODNmNzVhOTUzZGMzN2E1NmRlZjIyODY0MTI2YzA3NWU5ZjNhMzIyM2I2MDA0NWM1Mjc4Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjczMDU1OWZiZTY0MGY3MDg4YzE2OWZhOWJjZjU1ZTg3NzFhOTc5MTU5ZmI1YTA2MWNkODQzZTc2OGJjZDQyM2IifQ -->
### `client.user.login`

Operation ID: `loginUser`  
Route: `POST` `/user/auth/login`  
Equivalent member: `client.loginUser`  

#### Signature

```typescript
client.user.login<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authenticated session or MFA challenge | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.user.login();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsb2dpblVzZXIifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJ1c2VyLnN1Ym1pdFdhaXRsaXN0UmVxdWVzdCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJzdWJtaXRXYWl0bGlzdFJlcXVlc3QiLCJwYXRoIjoiL3VzZXIvYXV0aC93YWl0bGlzdCIsInJlc291cmNlIjoidXNlciIsInNlY3Rpb25fc2hhMjU2IjoiMjZjMWYyMTkxMTQ0NGU1NWM2N2UzOWQ5ZTY2Mzk4ODhiMDNkN2E0NmY1YTYwZjhjNGFiMWY4YTNjZDM3OGYxYyIsInNpZ25hdHVyZV9zaGEyNTYiOiI3NTQzZDlhMmYyZTNjNWZlYTA4Y2RhZjFmNGExNmJjYzVmZWYwOWIzZmEzYjcwYTU5YThjNmNiZjAyMzBiYTIyIn0 -->
### `client.user.submitWaitlistRequest`

Operation ID: `submitWaitlistRequest`  
Route: `POST` `/user/auth/waitlist`  
Equivalent member: `client.submitWaitlistRequest`  

#### Signature

```typescript
client.user.submitWaitlistRequest<Raw extends boolean = false>(requestOptions?: RequestOptions<Raw>): Promise<Raw extends true ? RawResponse<undefined> : undefined>;
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `202` | Waitlist request recorded with an opaque WL- reference | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```typescript
const result = await client.user.submitWaitlistRequest();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdWJtaXRXYWl0bGlzdFJlcXVlc3QifQ -->

