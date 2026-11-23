# JackAI Platform OS Hub API (public subset) .NET API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6ImM3Y2E1ZTVlYmI0YzA5MjkxMGVjNzJiMzcxZTE4ODMwMzM1OGM1ZTM0ZDI5MDhjMGE4OGY3ODJhMjQxMTYyY2YiLCJvcGVyYXRpb25fY291bnQiOjgsInJlbmRlcmVyIjoiZG90bmV0IiwidmVyc2lvbiI6IjEuNS4wIn0 -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `c7ca5e5ebb4c092910ec72b371e188303358c5e34d2908c0a88f782a241162cf`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **experimental**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Client hooks and tracing

`new ClientOptions { Hooks = new RequestHooks { ... } }` registers four callbacks. Every attempt starts with `BeforeRequest` and ends with exactly one of `OnRetry` (another attempt follows), `AfterResponse` (the success the call returns) or `OnError` (the failure the call reports). Each receives the operation id, the HTTP method, the URL, the request headers, the attempt number (from 1), the time elapsed since the call started and, once the server answered, the HTTP status. No context carries a credential: `Authorization`, `Proxy-Authorization`, `Cookie`, every API-key header and API-key query parameter, and any configured credential value read `[redacted]`. Every context is an immutable `HookContext` record: no hook can change the request.

`new ClientOptions { Tracer = ... }` opens one span per call through the tracer interface this SDK defines, named after the operation id, with `http.request.method`, `http.response.status_code` and `http.request.resend_count`. It needs no tracing library; README.md maps it onto the OpenTelemetry API.

## Resource `Health`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJIZWFsdGguR2V0QXN5bmMiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgiLCJwYXRoIjoiL2hlYWx0aCIsInJlc291cmNlIjoiSGVhbHRoIiwic2VjdGlvbl9zaGEyNTYiOiI5ZDNlNjRmYmI3ZGJjZDI4ZjMwYTU0MWFkNGIxZjBkM2YzNTY2Njc3OWE0MzVhMDRlZjIwNjkyMjIxOGM3N2I2Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjZkOGViZTBkYjI1NGY1ZTA1NDYxNmY2YzIyOTgwNzYxMDczZWRiZjhjZWE2N2YzZTliM2MxZmE4NzU5NjQ1MjkifQ -->
### `client.Health.GetAsync`

Operation ID: `getHealth`  
Route: `GET` `/health`  
Equivalent member: `client.GetHealthAsync`  

#### Signature

```csharp
public Task GetAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.Health.GetAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgifQ -->

## Resource `Kernel`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJLZXJuZWwuRmFpbFVzYWdlUXVvdGFBc3luYyIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJmYWlsVXNhZ2VRdW90YSIsInBhdGgiOiIvdjEva2VybmVsL3VzYWdlL2ZhaWwiLCJyZXNvdXJjZSI6Iktlcm5lbCIsInNlY3Rpb25fc2hhMjU2IjoiY2ViMDE5M2ViY2I2OWU0MmE3NjQ3YjhiOWY2MGM0ZDc0YzVkM2Y3OThlNjI1MTU2OGY4NzMyNDQ1ZjEyNjBjZiIsInNpZ25hdHVyZV9zaGEyNTYiOiJhZGQwZmY0MDgzZmZlYTBjNTQwNDMxMzlhNjA2NWI5NGFmYWEzNTM2OWQ4NjkwOTM3MWI0MmMxZDUwZDZkM2U3In0 -->
### `client.Kernel.FailUsageQuotaAsync`

Operation ID: `failUsageQuota`  
Route: `POST` `/v1/kernel/usage/fail`  
Equivalent member: `client.FailUsageQuotaAsync`  

#### Signature

```csharp
public Task FailUsageQuotaAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.Kernel.FailUsageQuotaAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmYWlsVXNhZ2VRdW90YSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJLZXJuZWwuRmluYWxpemVVc2FnZVF1b3RhQXN5bmMiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiZmluYWxpemVVc2FnZVF1b3RhIiwicGF0aCI6Ii92MS9rZXJuZWwvdXNhZ2UvZmluYWxpemUiLCJyZXNvdXJjZSI6Iktlcm5lbCIsInNlY3Rpb25fc2hhMjU2IjoiZGJlZGQ3NjVhYmJkY2M1ODNlOWY3NjU0MGQwNzlhNmQzZDQ4MGI0ODE5ZTJiOGFkMDY5Y2RlNjQ3ZWZkODdjMCIsInNpZ25hdHVyZV9zaGEyNTYiOiIwZGEyYzEyMzZmMjY2ZjJlYTJkNDBmMjEyYTVkNTBmMTVmYWRhNGUyNTU5NzMzZGQ1NGFkN2ZjZDZhNTk2YjY1In0 -->
### `client.Kernel.FinalizeUsageQuotaAsync`

Operation ID: `finalizeUsageQuota`  
Route: `POST` `/v1/kernel/usage/finalize`  
Equivalent member: `client.FinalizeUsageQuotaAsync`  

#### Signature

```csharp
public Task FinalizeUsageQuotaAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.Kernel.FinalizeUsageQuotaAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmaW5hbGl6ZVVzYWdlUXVvdGEifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJLZXJuZWwuUmVzZXJ2ZVVzYWdlUXVvdGFBc3luYyIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJyZXNlcnZlVXNhZ2VRdW90YSIsInBhdGgiOiIvdjEva2VybmVsL3VzYWdlL3Jlc2VydmUiLCJyZXNvdXJjZSI6Iktlcm5lbCIsInNlY3Rpb25fc2hhMjU2IjoiOWRhNmNkYmM5OWQ2NzhiNTE1ZmNhYzI2Njk4MWUzOWI2OTk0YzFmOTY4MDBlZmE3NmYzZDZlNTQ3ZGQzN2ViNSIsInNpZ25hdHVyZV9zaGEyNTYiOiI3YzkzZGM1NDQ3Mzg0Y2NkZTg4ODRiMThkZmJhOGVmMjM1YWEyNGQwMWM2NmExY2ZkMDE3Mzg1M2RlNDE5MWMwIn0 -->
### `client.Kernel.ReserveUsageQuotaAsync`

Operation ID: `reserveUsageQuota`  
Route: `POST` `/v1/kernel/usage/reserve`  
Equivalent member: `client.ReserveUsageQuotaAsync`  

#### Signature

```csharp
public Task ReserveUsageQuotaAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.Kernel.ReserveUsageQuotaAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZXNlcnZlVXNhZ2VRdW90YSJ9 -->

## Resource `User`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLkdldEN1cnJlbnRBc3luYyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldEN1cnJlbnRVc2VyIiwicGF0aCI6Ii91c2VyL21lIiwicmVzb3VyY2UiOiJVc2VyIiwic2VjdGlvbl9zaGEyNTYiOiJjOGMxYWI5ZjU5MjBjNGVmYjIyY2VhMmIwY2YxZjkxNzc5ZTI1ZmI5MDg0MmRmOWZkZDJmMWQ2YzgwMDFmMGJmIiwic2lnbmF0dXJlX3NoYTI1NiI6IjM1YTFkYTM4MzllZTVmYTM3M2EzMGM2ZTIxNDNhYWQ4OWNhZWVjMWQ1OTc1MDRiODk1MDA2ZGZjMzBhMzQyZjMifQ -->
### `client.User.GetCurrentAsync`

Operation ID: `getCurrentUser`  
Route: `GET` `/user/me`  
Equivalent member: `client.GetCurrentUserAsync`  

#### Signature

```csharp
public Task GetCurrentAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.User.GetCurrentAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRDdXJyZW50VXNlciJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLkdldFNpZ251cFBvbGljeUFzeW5jIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0U2lnbnVwUG9saWN5IiwicGF0aCI6Ii91c2VyL2F1dGgvc2lnbnVwLXBvbGljeSIsInJlc291cmNlIjoiVXNlciIsInNlY3Rpb25fc2hhMjU2IjoiZTY5NTY3NTNhNjU1YWVmYzdlMTMzYzc5MThhZDhiZDE1MzY2ZTBiNGMxZTJjMjg2YjExNDZiOTgwOTUwMzllZiIsInNpZ25hdHVyZV9zaGEyNTYiOiJiNDcyYmE1NjExMWNlZDY2MmJhYjk4ZDQyYmU2Y2JlZDVjMTMzNzY1NGViMTRkYzFhNTY3YTQ0YjJmNTM1YTBiIn0 -->
### `client.User.GetSignupPolicyAsync`

Operation ID: `getSignupPolicy`  
Route: `GET` `/user/auth/signup-policy`  
Equivalent member: `client.GetSignupPolicyAsync`  

#### Signature

```csharp
public Task GetSignupPolicyAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.User.GetSignupPolicyAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRTaWdudXBQb2xpY3kifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLkxvZ2luQXN5bmMiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoibG9naW5Vc2VyIiwicGF0aCI6Ii91c2VyL2F1dGgvbG9naW4iLCJyZXNvdXJjZSI6IlVzZXIiLCJzZWN0aW9uX3NoYTI1NiI6Ijg0ZDdjOTBhYmNkMjE4ZGQyZDdhNjMxYzcyMWZiNmUxMmVmYmYyZDJhMTZhNWZkOTk5ZGUwNjZkOThjZjU2OGQiLCJzaWduYXR1cmVfc2hhMjU2IjoiZGVmYzc3MzBlOGU0NWMzZDBiMDhlMGQ4YmI0OThkZmQ0YzVlMGIzNzE3ZTUxZWU5MDkzZWZmYTc4YWM1NjBmMiJ9 -->
### `client.User.LoginAsync`

Operation ID: `loginUser`  
Route: `POST` `/user/auth/login`  
Equivalent member: `client.LoginUserAsync`  

#### Signature

```csharp
public Task LoginAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.User.LoginAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsb2dpblVzZXIifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLlN1Ym1pdFdhaXRsaXN0UmVxdWVzdEFzeW5jIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6InN1Ym1pdFdhaXRsaXN0UmVxdWVzdCIsInBhdGgiOiIvdXNlci9hdXRoL3dhaXRsaXN0IiwicmVzb3VyY2UiOiJVc2VyIiwic2VjdGlvbl9zaGEyNTYiOiIyMTE0NjBjMGMzMGI5NTYyOWFiYzJjNzUyOWJjYzkxNzc3ZDBjZDFlNDRlOTI5MDA3NDJlYTkyMDVmMTNhNDFmIiwic2lnbmF0dXJlX3NoYTI1NiI6IjgwYTFiODViZTM1MGZjYzU2ZTJlMjBjNjJjMjliODc5ODcxODQ2MmE5NDQwYzk3N2M2YzdlZWUyYzNmMjY3YTMifQ -->
### `client.User.SubmitWaitlistRequestAsync`

Operation ID: `submitWaitlistRequest`  
Route: `POST` `/user/auth/waitlist`  
Equivalent member: `client.SubmitWaitlistRequestAsync`  

#### Signature

```csharp
public Task SubmitWaitlistRequestAsync(
RequestOptions? requestOptions = null,
CancellationToken cancellationToken = default)
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
```csharp
var result = await client.User.SubmitWaitlistRequestAsync();
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdWJtaXRXYWl0bGlzdFJlcXVlc3QifQ -->

