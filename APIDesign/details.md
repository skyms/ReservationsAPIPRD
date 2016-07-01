### Reservations – Display details

Get the details of a reservation using the _Reservations_ endpoint.

### Resource
```
GET /v1/reservations/{reservation\_id}
```
### Authorization

OAuth 2.0 bearer token with the request scope.

### Path Parameters

| Name | Type | Description |
| --- | --- | --- |
| reservation\_id | string | Unique identifier representing a Reservation. |

### Query Parameters

None

### Response

Status-Code: 200 OK
```json
{
	"reservation_id": "17cb78a7-b672-4d34-a288-a6c6e44d5315",
	"pickup_time": 1429294463,
	"reservation_status": "scheduled",
	"request_time": 1429294463,
	"product_id": "a1111c8c-c720-46c3-8534-2fcdd730040d",
	"start_latitude": 37.761492,
	"start_longitude": -122.423941,
	"start_nickname": null,
	"start_address": null,
	"start_place_id": null,
	"end_latitude": 37.775393,
	"end_longitude": -122.417546,
	"end_nickname": null,
	"end_address": null,
	"end_place_id": null,
	"payment_method_id": "a1111c8c-c720-46c3-8534-2fcdd730040d",
	"expense_code": null,
	"expense_memo": null
}
```

| Name | Type | Description |
| --- | --- | --- |
| reservation\_id | string | The unique ID of the Reservation. |
| product\_id | string | Unique identifier representing a specific product for a given latitude &amp; longitude. For example, uberX in San Francisco will have a different product\_id than uberX in Los Angeles. |
| reservation_status | string | 	The status of the reservation indicating state. Can be scheduled, cancelled or requested (already requested on behalf of user at the specified pickup time).|
| pickup\_time | integer | Unix UTC timestamp of when the user will be picked up. Note the pickup time is 15 minutes window start from the pickup\_time specified here. |
| start\_latitude | float | The beginning or &quot;pickup&quot; latitude. Either this or start\_place\_id must be specified. |
| start\_longitude | float | The beginning or &quot;pickup&quot; longitude. Either this or start\_place\_id must be specified. |
| start\_nickname(_optional_) | string | The beginning or &quot;pickup&quot; nickname label. |
| start\_address(_optional_) | string | The beginning or &quot;pickup&quot; address. |
| start\_place\_id(_optional_) | string | The beginning or &quot;pickup&quot; place ID. This is the name of an Uber saved place. Only &quot;home&quot; or &quot;work&quot; is acceptable. Either this or start\_latitude and start\_longitude must be specified. |
| end\_latitude (_optional_) | float | The final or destination latitude. Either this orend\_place\_id may be specified. |
| end\_longitude(_optional_) | float | The final or destination longitude. Either this orend\_place\_id may be specified. |
| end\_nickname (_optional_) | string | The final or destination nickname label. |
| end\_address (_optional_) | string | The final or destination address. |
| end\_place\_id (_optional_) | string | The final or destination place ID. This is the name of an Uber saved place. Only &quot;home&quot; or &quot;work&quot; is acceptable. Either this or end\_latitude andend\_longitude may be specified. |
| payment\_method\_id(_optional_) | string | The unique identifier of the payment method selected by a user. If set, the trip will be requested using this payment method. If not set, the trip will be requested using the user&#39;s last used payment method. |
| expense\_code (_optional_) | string | An alphanumeric identifier for expense reporting policies. This value will appear in the trip receipt and any configured expense-reporting integrations like  [Uber For Business](https://www.uber.com/business) or  [Business Profiles](https://www.uber.com/business/profiles). |
| expense\_memo (_optional_) | string | A free text field to describe the purpose of the trip for expense reporting. This value will appear in the trip receipt and any configured expense-reporting integrations like  [Uber For Business](https://www.uber.com/business) or [Business Profiles](https://www.uber.com/business/profiles). |

### Reservation Statuses

All possible statues of a Reservation&#39;s life cycle.

| Status | Description |
| --- | --- |
| scheduled | The reservation is already booked. The request will be sent at the user specified pick up time. |
| cancelled | The reservation has been cancelled. |
| requested | The reservation has been requested. This is the last stage of reservation. The reservation will become a request at the specified time.|
