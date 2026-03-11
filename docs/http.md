# HTTP

## HttpRequestBuilder

Fluent builder for HTTP requests with method chaining support

### Methods

#### `HttpRequestBuilder:get()`

Set HTTP method to GET

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:post()`

Set HTTP method to POST

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:header(key, value)`

Add a single HTTP header

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `key` | `string` | Header name |
| `value` | `string` | Header value |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:headers(headers_table)`

Add multiple HTTP headers from a table

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `headers_table` | `table<string, string>` | Table of header key-value pairs |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:bearer(token)`

Add Bearer token authorization header

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `token` | `string` | Bearer token |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:user_agent(ua)`

Set User-Agent header

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `ua` | `string` | User agent string |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:basic_auth(username, password)`

Add Basic authentication header

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `username` | `string` | Username for basic auth |
| `password` | `string` | Password for basic auth |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:accept_json()`

Add Accept: application/json header

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:json(json_data)`

Set request body as JSON

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `json_data` | `table` | Lua table to serialize as JSON |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:form(form_data)`

Set request body as form data (application/x-www-form-urlencoded)

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `form_data` | `table<string, string>` | Form fields as key-value pairs |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:body(raw_body)`

Set raw request body

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `raw_body` | `string` | Raw body content |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:query(query_params)`

Add query parameters to URL

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `query_params` | `table<string, string\|number>` | Query parameters as key-value pairs |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:timeout(seconds)`

Set request timeout in seconds

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `seconds` | `integer` | Timeout in seconds |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:connect_timeout(seconds)`

Set connection timeout in seconds

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `seconds` | `integer` | Connection timeout in seconds |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:tls_pin(pin)`

Set TLS certificate pinning

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `pin` | `string` | TLS pin hash |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:no_revoke(no_revoke)`

Control certificate revocation checking

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `no_revoke` | `boolean` | If true, disable revocation checks |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:param(param)`

Add custom parameter to request.
Will be passed back in response callback as a 4th argument.

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `param` | `any` | Custom parameter value |

**Returns:** `HttpRequestBuilder`

#### `HttpRequestBuilder:send(callback)`

Send HTTP request with callback for response handling

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `callback` | `fun(status_code: number, response_body: string, success: boolean, custom_param: any): nil` |  |

#### `HttpRequestBuilder:send_and_forget()`

Send HTTP request without waiting for response (fire and forget)

## http

### Methods

#### `http.request(url)`

Create a new HTTP request builder

**Parameters:**

| Name | Type | Description |
|------|------|-------------|
| `url` | `string` | The URL to make request to |

**Returns:** `HttpRequestBuilder`
