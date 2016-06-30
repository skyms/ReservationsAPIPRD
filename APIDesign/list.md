
### Displaying Details of a Reservations

Get the status of an ongoing or completed trip that was created using the _Reservations_ endpoint.

### Resource

GET /v1/reservation/{reservation\_id}

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

{

   &quot;reservation\_id&quot;:&quot;17cb78a7-b672-4d34-a288-a6c6e44d5315&quot;,

   &quot;pickup\_time&quot;: 1429294463,

   &quot;reservation\_status&quot;:&quot;scheduled&quot;,

   &quot;request\_time&quot;: 1429294463,

   &quot;product\_id&quot;: &quot;a1111c8c-c720-46c3-8534-2fcdd730040d&quot;,

   &quot;start\_latitude&quot;: 37.761492,

   &quot;start\_longitude&quot;: -122.423941,

   &quot;end\_latitude&quot;: 37.775393,

   &quot;end\_longitude&quot;: -122.417546,

}

| Name | Type | Description |
| --- | --- | --- |
| reservation\_id | string | The unique ID of the Reservation. |
| product\_id | string | Unique identifier representing a specific product for a given latitude &amp; longitude. For example, uberX in San Francisco will have a different product\_id than uberX in Los Angeles. |
| status | string | The status of the Request indicating state. |
| pickup\_time | integer | Unix UTC timestamp of when the user will be picked up. Note the pickup time is 15 minutes window start from the pickup\_time specified here. |
| product\_id (_optional_) | string | The unique ID of the product being requested. If none is provided, it will default to the cheapest product for the given location. |
| start\_latitude(_optional_) | float | The beginning or &quot;pickup&quot; latitude. Either this or start\_place\_id must be specified. |
| start\_longitude(_optional_) | float | The beginning or &quot;pickup&quot; longitude. Either this or start\_place\_id must be specified. |
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
