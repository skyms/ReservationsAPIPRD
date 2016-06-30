## Reservations
Reservations object is a collection of reservations made by user. Reservations object support pagination with offset, limit and count.
### Properties
| Name | Type | Description |
| --- | --- | --- |
| offset | string | The unique ID of the Reservation. |
| limit | string | Unique identifier representing a specific product for a given latitude &amp; longitude. For example, uberX in San Francisco will have a different product\_id than uberX in Los Angeles. |
| count | string | The status of the Request indicating state. |
| reservations |Reservation[]| An array of existing reservations.|



## Reservation
Reservation object represents a reservation made by user and includes all details of the reservation.
### Properties
| Name | Type | Description |
| --- | --- | --- |
| reservation\_id | string | The unique ID of the Reservation. |
| product\_id | string | Unique identifier representing a specific product for a given latitude &amp; longitude. For example, uberX in San Francisco will have a different product\_id than uberX in Los Angeles. |
| reservation\_status | string | The status of the Request indicating state. |
| pickup\_time | integer | Unix UTC timestamp of when the user will be picked up. Note the pickup time is 15 minutes window start from the pickup\_time specified here. |
| request\_time | integer | Unix UTC timestamp of when the reservation is made. |
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
| expense\_code (_optional_) | string | An alphanumeric identifier for expense reporting policies. This value will appear in the trip receipt and any configured expense-reporting integrations like  [**Uber For Business**](https://www.uber.com/business) or  [**Business Profiles**](https://www.uber.com/business/profiles). |
| expense\_memo (_optional_) | string | A free text field to describe the purpose of the trip for expense reporting. This value will appear in the trip receipt and any configured expense-reporting integrations like  [**Uber For Business**](https://www.uber.com/business) or [**Business Profiles**](https://www.uber.com/business/profiles). |
