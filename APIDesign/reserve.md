### Reservations - Create

The _Reservations_ endpoint allows a ride to be scheduled on behalf of an Uber user.

### Resource
```
POST /v1/reservations
```

### Authorization

OAuth 2.0 bearer token with the request scope.

### POST Parameters

| Name | Type | Description |
| --- | --- | --- |
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

### Example

When specifying pickup and drop-off locations, you can either use latitude/longitude pairs or a place ID. A place ID is just the name of an Uber saved place. Currently only &quot;home&quot; or &quot;work&quot; is acceptable.

```json
{
	"pickup_time": 1429294463,
	"product_id": "a1111c8c-c720-46c3-8534-2fcdd730040d",
	"start_latitude": 37.761492,
	"start_longitude": -122.423941,
	"end_latitude": 37.775393,
	"end_longitude": -122.417546

}

```

or
```json
{
	"pickup_time": 1429294463,
	"product_id": "a1111c8c-c720-46c3-8534-2fcdd730040d",
	"start_place_id": "home",
	"end_place_id": "work"
}
```

### Response

Status-Code: 202 OK
```json
{
   "reservation_id": "852b8fdd-4369-4659-9628-e122662ad257",
   "product_id": "a1111c8c-c720-46c3-8534-2fcdd730040d",
   "status": "scheduled",
   "pickup_time": 1429294463,
   "start_latitude": 37.761492,
   "start_longitude": -122.423941,
   "end_latitude": 37.775393,
   "end_longitude": -122.417546,
   "request_time": 1429234463
}

```

| Name | Type | Description |
| --- | --- | --- |
| reservation\_id | string | The unique ID of the Reservation/Scheduled Ride. |
| product\_id | string | Unique identifier representing a specific product for a given latitude &amp; longitude. For example, uberX in San Francisco will have a different product\_id than uberX in Los Angeles. |
| reservation_status | string | The status of the reservations indicating state. Can be scheduled, cancelled or requested (already requested on behalf of user at the specified pickup time).|
| pickup\_time | integer | Unix UTC timestamp of when the user will be picked up. Note the pickup time is 15 minutes window start from the pickup\_time specified here. |
| pickup\_latitude | float | The latitude of the pickup. |
| pickup\_longitude | float | The longitude of the pickup. |
| end.latitude | float | The latitude of the destination. |
| end.longitude | float | The longitude of the destination. |

### Error Responses

Status-Code: 409 Conflict
```json
{
   "error":
      {
         "status": 400,
         "code": "invalid_payment",
         "title": "The rider's payment method is invalid. The user must update the billing info."
      }
   
}

```

### Other Possible Errors

| Error | Code | Description |
| --- | --- | --- |
| 400 | unconfirmed\_email | The user hasn&#39;t confirmed their email address. Instruct the user to confirm their email address within the native mobile application or by visiting [https://riders.uber.com](https://riders.uber.com/). |
| 400 | invalid\_payment | The rider&#39;s payment method is invalid. The user must update the billing info. |
| 403 | forbidden | This user is forbidden from making a request at this time and should consult our support team by visiting  [https://help.uber.com](https://help.uber.com/) or by emailing [support@uber.com](mailto:support@uber.com). |
| 403 | unverified | The user hasn&#39;t confirmed their mobile number. Instruct the user to confirm their mobile phone number within the native mobile application or by visiting [https://riders.uber.com](https://riders.uber.com/). |
| 403 | product\_not\_allowed | The product being requested is not available to the user. Have them select a different product to successfully make a request. |
| 403 | pay\_balance | The rider has an outstanding balance and must update her account settings by using the native mobile application or by visiting  [https://riders.uber.com](https://riders.uber.com/). |
| 403 | user\_not\_allowed | User is banned and is not permitted to request a ride. |
| 403 | too\_many\_cancelations | The rider is temporarily blocked due to cancelling too many times. |
| 403 | missing\_national\_id | Certain jurisdictions require Uber users to register their national ID number or passport number before taking a ride. If a user receives this error when booking a trip through the Developer API, they must enter their national ID number or passport number through the Uber iOS or Android app. |
| 404 | not\_found | An invalid product ID was requested. Retry the API call with a valid product ID. |
| 409 | missing\_payment\_method | The rider must have at least one payment method on file to request a car. The rider must add a payment method by using the native mobile application or by visiting  [https://riders.uber.com](https://riders.uber.com/). |
| 409 | surge | Surge pricing is currently in effect for this product. Please have the user confirm surge pricing by sending them to the surge\_confirmation\_href described in the Request Tutorial. |
| 409 | retry\_request | An error has occurred when the attempting to request a product. Please reattempt the request on behalf of the user. |
| 409 | trip\_exists | The trip has already been scheduled. |
| 422 | destination\_required | This product requires setting a destination for ride requests. |
| 500 | internal\_server\_error | An unknown error has occurred. |


