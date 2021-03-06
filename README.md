# Reservations API PRD V1.0

### Objectives
Tap a button, get a ride in minutes – that’s the Uber promise in more than 400 cities worldwide. And now Uber is changing the way for people to get around once again. By offering the magic in a 3rd party app to schedule a ride directly, Uber users can plan ahead and be smart about future transportation needs. Scheduling a ride exactly when users realize their needs make Uber reservations the most natural, convenient and engaging way for both new users and existing users to get a ride. 

#### For Uber
- **Attract Users**. Whichever app users are using, whenever there is a need for future transportation. Users can easily schedule the ride right there in context. This reduce the possibility of user choosing alternative in the future when booking. The convenience and in context will attract users to Uber ecosystem for all transportation needs.
- **Competitor advantages**. Since users can schedule the ride right within the app, this brings great convenience to users and also users are much less likely to cancel the ride and switch to competitors at the time of picking up.
- **Improve experience**. The seamless and worry free scheduling experience will keep users engaged with Uber.
- **Increase revenue**. With a simple and efficient scheduling, much stronger in competition and new users brought in through 3 party app, there are will be more rides taken with Uber and more revenue. 
- **Marketing/Branding**. With Uber logo built into more apps, Uber actually is advertising for free.
- **Better allocate resource ** Uber can be smarter about resource when we know the demand ahead of time.


#### For developers/3rd party
- **Improve experience**. For developers, for example, airlines, restaurants, Uber scheduling solve the last mile problem and offer a simple, integrated experience to their users. 
- **Increase revenue. With Uber affiliate program and more happily engaged users, developers could benefit financially.
- **Retain users**. Since Uber scheduling brings a great end-to-end experience, developers could retain more users. Uber loyalty program with partners could also help retaining users.
- **Marketing** Through co-marketing. Developer can get more exposure through uber's marketing channels.

#### For Uber riders
- Improve experience. Uber is accessible everywhere and in any situation, which gives users easy and contextual access to their travel needs.
-  Extra rewards. With Uber loyalty program especially with travel partners, users can enjoy convenience and rewards at the same time. They can get bonus points if they schedule a ride as part of their travel.

### Scope
#### In Scope
APIs will enable the same scenario as UI within the Uber app. The major use cases are.
- Allow riders to schedule a ride at a future time for a specified pickup and dropoff location.
- Allow riders to cancel a ride before the scheduled pick up time.
- Allow riders to review and update the reservations.

#### Out of Scope 
- If surge happens at the time of requesting a ride, User will automatically accept the surge or follow the same behavior as Uber app. (This is worth debating, I prefer automatically accept as the point of reservations is that users don't need to worry about it anymore. But this depends on legal obligations and other factors. One other way is to set a surge threshold and only ask for confirmation when it is beyond.)
- No driver available at the time of requesting. This depends on the actual implementation of Uber. If Uber sends out the request at the specified pickup time, then this could happen. Again, API will behave the same as UI.
- No Uber Pool support. There's no way to predict the availability of Uber pool in the future. In the future, there could do a Uber Pool/UberX combo option though.

#### Future Features
- A widget that developers can simply add to their app to help schedule a ride with Uber.
- When users schedule a ride, Uber should be smart enough to suggest a time based on origin and destination.
- Webhook on status changed. Uber is able to notify users when the status of a reservation change. For example, User gets notified when the reservation has been requested. 
- Reservations for Uber Pool/ Uber X combo.
- Reservation(Delivery window) for Uber eats and Uber Rush.
- Better Surge handling.
- Better exception handling. For example, no driver available.
- Trip branding.

### Users

| Vertical | Example Customer | User Cases Description | Details |
| --- | --- | --- | --- |
| Airlines/Travel Booking | Delta Air Lines | Reserve a ride to the airport after user checks in. |   |
| Airlines/Travel Booking | Expedia | Reserve a ride to the hotel from the airport after landing.Reserve a ride to the airport after user checks in. |   |
| Calendar App | Outlook | Reserve a ride in the morning before the user&#39;s earliest meetingReserve a ride for me around the time users is about to leave work.Reserve a ride for me when user is heading to a meeting |   |
| Dinning/Events/All sorts of reservations | Open Table, Trip advisor, tickets, myTime | Reserve a ride to the restaurant after a user makes his reservation. |   |
| Smart home and assistant | Amazon Echo, Siri, Google, Cortana | Just a voice command to ask assistant to book a right in the futureAssistant can be smart about user&#39;s schedule, similar to Calendar.Integrate with other skills Assistant has including booking and reservations. |   |
| Social networking and Messaging | Facebook, iMessage, Snapchat | Understand the conversation and suggest reserving an Uber ride in the context.  |   |
| Event organizers | EviteUber for Business | Event organizer can schedule a ride for participants, improving attendance. | |

### API Design

#### Reservation Flow 
![alt text](https://github.com/skyms/ReservationsAPIPRD/blob/master/images/Flow.png "Flow")


#### [Endpoints](/APIDesign/endpoints.md) 
-[Reservations](https://github.com/skyms/ReservationsAPIPRD/blob/master/APIDesign/endpoints.md#reservations) 
-[Reservation](https://github.com/skyms/ReservationsAPIPRD/blob/master/APIDesign/endpoints.md#reservation) 
#### [Reserve a ride](/APIDesign/reserve.md) (Click the link for detailed API design)
```
POST /reservations
```
#### [List all reservations](/APIDesign/list.md) (Click the link for detailed API design)
```
GET /reservations
```

#### [Show details of a reservation](/APIDesign/details.md)(Click the link for detailed API design)
```
GET /reservations/{reservation_id}
```

#### [Cancel a reservation](/APIDesign/cancel.md)(Click the link for detailed API design)
```
DELETE /reservations/{reservation_id}
```

### Metrics
Metrics

Success Metrics

I think the success of API includes business success, service health success and developer community success.

Business success should align with company goals and strategy. I believe Uber&#39;s focuses now are users, usage and monetization. Therefore, for this API, we would define the success in the same way. Since I don&#39;t have the data at hand, I will use percentage instead.

Business Success Metrics

| Goals | Metrics | Goals |
| --- | --- | --- |
| Increase users | How many new users signed up through third party app while trying to make a reservation? | 5000 daily (assuming Uber has 100K new users daily, this account for 5%) |
| Increase usage | How many rides are taken from reservations made by API? | 150K daily rides (roughly 15% of Uber&#39;s daily rides) |
| Increase Revenue | What&#39;s the revenue coming from ride made through reservation by thrid party app | US$ 600K daily ($20/ride \* 150K ride \*20% cut)   |

Service Health Metrics

| Metrics | Goals |
| --- | --- |
| Service uptime | 99.999% |
| Error Rate | &lt;0.11% |
| Average API call Performance | &lt;500ms |



Developer community Health Metrics

| Metrics | Goals |
| --- | --- |
| Total Apps interacting with reservations within 6 months | 30 |

We should also consider qualitative feedback including sentiment on social network, forums  and survey results.

### Go To Market

Attract, Aware, Inspire, Promote, Engage and Support.
- **Attract: Goals, values and resource** Attract developers by positioning API values directly to their needs. Understand each vertical and what developers are trying to achieve. Position our API to deliver unique values that are appealing. In addition, identify the resource available to bring this product to market, including marketing, sales, DX etc. More importantly, define the success of this product.
- **Aware: Active developer program and experience** Drive awareness of the upcoming APIs from the beginning of the project. Build an active developer program and really engage with this community (in this case, Uber developer program). In the early design phase, socialize API design with developer community, collect their feedback and make them aware and excited about the upcoming APIs. This will also carry on to over APIs as well. This will be a huge treasure along the way and these developers will become really engaged and actually promote for us. Have monthly newsletter and open channels to communicate would also help the program active.
- **Inspire: Strategic partnership** Inspire developers by showcasing customer evidences. Identify key strategic partners in each verticals and work closely with them to release the pilot apps using the reservations APIs. For example, Delta airlines, Open Table, Amazon Echo etc. These will be role models for the mass market and educate developers with the potentials and applications of these APIs. Eventually this will inspire developers to build even more.
- **Promote** Have the big announcement and promote APIs in the right opportunity, usually a big conference/event. Then all the marketing materials should be ready and marketing campaigns should be in place to keep the momentum, including press coverage, blog post, social network coverage, partner marketing, direct mailing list.  
- **Engage: Hackathons and conferences** Host hackathons and present at related industry or developer conferences to get developers try out the APIs and engaged. Hands on experiences can really keep them engaged and usually many exciting ideas come out of Hackathons.
- **Support: DX, community and documentation** Update the dev portal and documentation to make sure it is really easy for developers to get started and get support whenever they need it. 
- ** Measure effectiveness of marketing plan and adjust accordingly ** Different developer communities may have different preferences even in marketing program. We need to measure not only the success of product but also marketing. Invest in where it is more effective.
- **Co-marketing** Co marketing with strategic partners is a win-win scenario for both parties.
- **Financial incentives** Financial incentives could stimulate the developers as well. The Uber affiliate program is a great opportunity to Mmotivate developers to interact with Uber and help Uber reach out to more users.

##### Why my marketing program works?
- My marketing programs have a clear message to developers. These reservations APIs are simple to use and benefits developers’ business as well as Uber.
- My marketing plans are clear about the values these APIs added to developers' business and also showcase and inspire them how they can leverage these API and move forward in their business together with Uber.
- My marketing plan reaches out to developers in the most natural and effective way. No matter it is an active developer program, a developer conference or hackathon. These are all the things developers are interested and familiar with. These are the channels they are more willing to communicate and accept the marketing message.
- My marketing plan have early involvement with strategic partners. Early involvements offers the opportunity to get early feedback, have more handholding work and finally really showcase what high quality apps are like. These not only help convince mass developer community but also act as role models.
- My marketing plans are data driven.  We should measure the effectiveness of each marketing channels and adjust accordingly. Always make sure the investment goes to the most effective channels.


Yu Liu All Rights Reserved, 2016
