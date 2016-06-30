List all reservations

### GET /v1.2/reservations

### User Activity (v1.2)

The _User Activity_ endpoint returns a limited amount of data about a user&#39;s lifetime activity with Uber. The response will include pickup and dropoff times, the city the trips took place in, the distance of past requests, and information about which products were requested.

The history array in the response will have a maximum length based on the limit parameter. The response value countmay exceed limit, therefore subsequent API requests may be necessary.

### Resource

GET /v1.2/reservations

### Authorization

OAuth 2.0 bearer token with the history or reservations\_lite scope.

### Query Parameters

| Name | Type | Description |
| --- | --- | --- |
| offset (_optional_) | integer | Offset the list of returned results by this amount. Default is zero. |
| limit (_optional_) | integer | Number of items to retrieve. Default is 5, maximum is 50. |

### Response

Status-Code: 200 OK
```json
{

 offset: 0,

 limit: 1,

 count: 5,

 reservation: [

    {

  reservation\_id:852b8fdd-4369-4659-9628-e122662ad257,

  product\_id:a1111c8c-c720-46c3-8534-2fcdd730040d,

  status:scheduled,

  pickup\_time: 1429294463,

  start\_latitude: 37.761492,

  start\_longitude: -122.423941,

  end\_latitude: 37.775393,

  end\_longitude: -122.417546,

  request\_time: 1429234463

  },

  ]

}
```

| Name | Type | Description |
| --- | --- | --- |
| offset | integer | Position in pagination. |
| limit | integer | Number of items to retrieve (50 max). |
| count | integer | Total number of items available. |
| reservation[].reservation\_id | string | The unique ID of the Reservation. |
| reservation[].product\_id | string | Unique identifier representing a specific product for a given latitude &amp; longitude. For example, uberX in San Francisco will have a different product\_id than uberX in Los Angeles. |
| reservation[].status | string | The status of the Request indicating state. |
| reservation[].pickup\_time | integer | Unix UTC timestamp of when the user will be picked up. Note the pickup time is 15 minutes window start from the pickup\_time specified here. |
| reservation[].product\_id (_optional_) | string | The unique ID of the product being requested. If none is provided, it will default to the cheapest product for the given location. |
| reservation[].start\_latitude(_optional_) | float | The beginning orpickup latitude. Either this or start\_place\_id must be specified. |
| reservation[].start\_longitude(_optional_) | float | The beginning orpickup longitude. Either this or start\_place\_id must be specified. |
| reservation[].start\_nickname(_optional_) | string | The beginning orpickup nickname label. |
| reservation[].start\_address(_optional_) | string | The beginning orpickup address. |
| reservation[].start\_place\_id(_optional_) | string | The beginning orpickup place ID. This is the name of an Uber saved place. Onlyhome orwork is acceptable. Either this or start\_latitude and start\_longitude must be specified. |
| reservation[].end\_latitude (_optional_) | float | The final or destination latitude. Either this orend\_place\_id may be specified. |
| reservation[].end\_longitude(_optional_) | float | The final or destination longitude. Either this orend\_place\_id may be specified. |
| reservation[].end\_nickname (_optional_) | string | The final or destination nickname label. |
| reservation[].end\_address (_optional_) | string | The final or destination address. |
| reservation[].end\_place\_id (_optional_) | string | The final or destination place ID. This is the name of an Uber saved place. Onlyhome orwork is acceptable. Either this or end\_latitude andend\_longitude may be specified. |
| reservation[].payment\_method\_id(_optional_) | string | The unique identifier of the payment method selected by a user. If set, the trip will be requested using this payment method. If not set, the trip will be requested using the user&#39;s last used payment method. |
| reservation[].expense\_code (_optional_) | string | An alphanumeric identifier for expense reporting policies. This value will appear in the trip receipt and any configured expense-reporting integrations like  [Uber For Business](https://www.uber.com/business) or  [Business Profiles](https://www.uber.com/business/profiles). |
| reservation[].expense\_memo (_optional_) | string | A free text field to describe the purpose of the trip for expense reporting. This value will appear in the trip receipt and any configured expense-reporting integrations like  [Uber For Business](https://www.uber.com/business) or [Business Profiles](https://www.uber.com/business/profiles). |
