



### Displaying Details of a Reservations

Get the status of an ongoing or completed trip that was created using the _Reservations_ endpoint.

### Resource
```
GET /v1/reservation/{reservation\_id}
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
   "reservation_id":"17cb78a7-b672-4d34-a288-a6c6e44d5315",
   "pickup_time": 1429294463,
   "reservation_status":"scheduled",
   "request_time": 1429294463,
   "product_id": "a1111c8c-c720-46c3-8534-2fcdd730040d",  
   "start_latitude": 37.761492,
   "start_longitude": -122.423941,
   "start_nickname": null,
   "start_address":null,
   "start_place_id": null,
   "end_latitude": 37.775393,
   "end_longitude": -122.417546,
   "end_nickname": null,
   "end_address":null,
   "end_place_id": null,
   "payment_method_id":"a1111c8c-c720-46c3-8534-2fcdd730040d",
   "expense_code":null,
   "expense_memo":null
}
```

| Name | Type | Description |
| --- | --- | --- |
| reservation\_id | string | The unique ID of the Reservation. |
| product\_id | string | Unique identifier representing a specific product for a given latitude &amp; longitude. For example, uberX in San Francisco will have a different product\_id than uberX in Los Angeles. |
| reservation_status | string | The status of the Request indicating state. |
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

### Request Statuses

All possible statues of a Request&#39;s life cycle.

| Status | Description |
| --- | --- |
| processing | The Request is matching to the most efficient available driver. |
| no\_drivers\_available | The Request was unfulfilled because no drivers were available. |
| accepted | The Request has been accepted by a driver and is &quot;en route&quot; to the start location (i.e.start\_latitude and start\_longitude). |
| arriving | The driver has arrived or will be shortly. |
| in\_progress | The Request is &quot;en route&quot; from the start location to the end location. |
| driver\_canceled | The Request has been canceled by the driver. |
| rider\_canceled | The Request canceled by rider. |
| completed | Request has been completed by the driver. |
