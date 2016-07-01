# Reservations API PRD V1.0

### Objectives
Tap a button, get a ride in minutes – that’s the Uber promise in more than 400 cities worldwide. And now Uber is changing the way for people to get around once again. By offering the magic in a 3rd party app to schedule a ride directly, Uber users can plan ahead and be smart about future transportation needs. Scheduling a ride exactly when users realize their needs make Uber reservations the most natural, convenient and engaging way for both new users and existing users to get a ride. 

#### For Uber
- Attract Users. Whichever app users are using, whenever there is a need for future transportation. Users can easily schedule the ride right there in context. This reduce the possibility of user choosing alternative in the future when booking. The convenience and in context will attract users to Uber ecosystem for all transportation needs.
- Competitor advantages. Since users can schedule the ride right within the app, this brings great convenience to users and also users are much less likely to cancel the ride and switch to competitors at the time of picking up.
- Improve experience. The seamless and worry free scheduling experience will keep users engaged with Uber.
- Increase revenue. With a simple and efficient scheduling, much stronger in competition and new users brought in through 3 party app, there are will be more rides taken with Uber and more revenue. 
- Marketing/Branding. With Uber logo built into more apps, Uber actually is advertising for free.


#### For developers/3rd party
- Improve experience. For developers, for example, airlines, restaurants, Uber scheduling solve the last mile problem and offer a simple, integrated experience to their users. 
- Increase revenue. With Uber affiliate program and more happily engaged users, developers could benefit financially.
- Retain users. Since Uber scheduling brings a great end-to-end experience, developers could retain more users. Uber loyalty program with partners could also help retaining users.

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
- If surge happens at the time of requesting a ride, User will automatically accept the surge or follow the same behavior as Uber app. (This worth debating, I prefer automatically accept as the point of reservations is that users don't need to worry about it anymore. But this depends on legal obligations and other factors. One other way is to set a surge threshold and only ask for confirmation when it is beyond.)
- No driver available at the time of requesting. This depends on the actual implementation of Uber. If Uber sends out the request at the specified pickup time, then this could happen. Again, API will behave the same as UI.
- No Uber Pool support. There's no way to predict the availability of Uber pool in the future. In the future, there could do a Uber Pool/UberX combo option though.

#### Future Features
- Uber Pool/ Uber X combo.
- Uber eats.
- Better Surge handling.
- Better exception handling.
- Trip branding.
- Webhook on status changed.
- smart suggest pick up time based on destination.
- a widget for developers to easily adopt this feature.

### Users

| Industry | Example Customer | Description |Details|
| --- | --- | --- | --- |
|Smart Home| Amazon Echo, Google home| Schedule a ride for the future with a simple voice command or based on conversation | Details|
|Personal Assistant| Siri, Google | |Details|
|Social| Messenger, iMessage | |Details|
|Airlines| Delta | |Details|
|Restaurants, event venues, movies| Open Table | |Details|
|Commute| Outlook | |Details|
|Event Organizer| Enterprise | |Details|

### API Design
#### [Endpoints](/APIDesign/endpoints.md) 
#### [Reserve a ride](/APIDesign/schedule.md)
```
POST /reservations
```
#### [List all reservations](/APIDesign/list.md)
```
GET /reservations
```

#### [Show details of a reservation](/APIDesign/details.md)
```
GET /reservations/{reservation_id}
```

#### [Cancel a reservation](/APIDesign/cancel.md)
```
DELETE /reservations/{reservation_id}
```

### Metrics
User aquisition
increase footprint
increase stickiness
revenue
new line of business

- Developers/app registered, number of partners, active developers, trending apps top developers
- dev portal funnel
- API call volumes
- API-generated revenue
- API-generated new users
- API-generated rides

Service uptime
API performance
calls per method
errors
percentage of error

qualitative feedbacks, surveys, testing, forums, social media

### Go To Market

Attract, Aware, Inspire
- **Attract: Goals, values and resource** Attract developers by positioning API values directly to their needs. Understand each vertical and what developers are trying to achieve. Position our API to deliver unique values that are appealing. In addition, identify the resource available to bring this product to market, including marketing, sales, DX etc. More importantly, define the success of this product.
- **Aware: Active developer program and experience** Drive awareness of the upcoming APIs from the beginning of the project. Build an active developer program and really engage with this community (in this case, Uber developer program). In the early design phase, socialize API design with developer community, collect their feedback and make them aware and excited about the upcoming APIs. This will also carry on to over APIs as well. This will be a huge treasure along the way and these developers will become really engaged and actually promote for us. Have monthly newsletter and open channels to communicate would also help the program active.
- **Inspire: Strategic partnership** Inspire developers by showcasing customer evidences. Identify key strategic partners in each verticals and work closely with them to release the pilot apps using the reservations APIs. For example, Delta airlines, Open Table, Amazon Echo etc. These will be role models for the mass market and educate developers with the potentials and applications of these APIs. Eventually this will inspire developers to build even more.
- **Promote** Have the big announcement and promote APIs in the right opportunity, usually a big conference/event. Then all the marketing materials should be ready and marketing campaigns should be in place to keep the momentum, including press coverage, blog post, social network coverage, partner marketing, direct mailing list.  
- **Engage: Hackathons and conferences** Host hackathons and present at related industry or developer conferences to get developers try out the APIs and engaged. Hands on experiences can really keep them engaged and usually many exciting ideas come out of Hackathons.
- **Support: DX, community and documentation** Update the dev portal and documentation to make sure it is really easy for developers to get started and get support whenever they need it. 
- ** Co-marketing** Co marketing with strategic partners is a win-win scenario for both parties.
- ** Financial incentives** Financial incentives could stimulate the developers as well. The Uber affiliate program is a great opportunity to motivate developers to interact with Uber and help Uber reach out to more users. 






