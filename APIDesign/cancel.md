

#### Ride Request - Cancel

Cancel a reservation on behalf of a rider.

### Resource

DELETE /v1/requests/{reservation\_id}

### Authorization

OAuth 2.0 bearer token with the request scope.

### Path Parameters

| Name | Type | Description |
| --- | --- | --- |
| reservation\_id | string | Unique identifier representing a reservation. |

### Query Parameters

None

### Response

Status-Code: 204 Success

###  Error Responses

| Status Code | Code | Message |
| --- | --- | --- |
| 401 | unauthorized | Invalid OAuth 2.0 Credentials provided. |
| 403 | forbidden | Forbidden |
| 409 | already cancelled | The reservation has been cancelled already. |

