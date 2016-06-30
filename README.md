# Reservations API PRD V1.0

### Objectives
Tap a button, get a ride in minutes – that’s the Uber promise in more than 400 cities worldwide. And now Uber is changing the way for people to get around once again. By offering the magic in a 3rd party app to schedule a ride direcly, Uber users can plan ahead and be smart about future transportation needs. Scheduling a ride exactly when users realize their needs make Uber reservations the most natural, conveneint and engageing way for both new users and exsiting users to get a ride. 

#### For Uber
- Attract Users. Whichever app users are using, whenever there is a need for future transportation. Users can easily schedule the ride right there in context. This reduce the possibility of user choosing alternative in the future when booking. The convenience and in context will attract users to Uber ecosystem for all transportation needs.
- Competitor advantages.Since users can schedule the ride right within the app, this brings great convenience to users and also users are much less likely to cancel the ride and switch to competitors at the time of picking up.
- Improve experience. The seamless and worry free scheduling experience will keep users engaged with Uber.
- Increase revenue. With a simple and efficient scheduling, much stronger in competitition and new users brought in through 3 party app, there are will be more rides taken with Uber and more revenue. 
- Marketing/Branding. With Uber logo built into more apps, Uber actually is advertising for free.


#### For developers/3rd party
- Improve experience. For developers, for example, airlines, restaurants, Uber scheduling solve the last mile problem and offer a simple, integrated experience to their users. 
- Increase revenue. With Uber affiliate program and more happily engaged users, developers could benefit financially.
- Retain users. Since Uber scheduling brings a great end-to-end experience, developers could retain more users. Uber loyalty program with partners could also help retaining users.

#### For Uber riders
- Improve experience. Uber is accessbile everywhere and in any situation, which gives users easy and contextual access to their travel needs.
-  Extra rewards. With Uber loyalty program especially with travel partners, users can enjoy convenience and rewards at the same time. They can get bonus points if they schedule a ride as part of their travel.

### Scope
#### In Scope
APIs will enable the same scenario as UI within the Uber app. The major use cases are.
- Allow riders to schedule a ride at a future time for a specified pickup and dropoff location.
- Allow riders to cancel a ride before the scheduled pick up time.
- Allow riders to review and update the reservations.

#### Out of Scope 
- If surge happens at the time of requesting a ride, User will automatically accept the surge or follow the same behavior as Uber app. (This worht debating, I prefer automatically accept as the point of reservations is that users don't need to worry about it any more. But this depends on legal obligations and other factors. One other way is to set a surge threshold and only ask for confirmation when it is beyond.)
- No driver available at the time of requesting. This depends on the actual implemenation of Uber. If Uber sends out the request at the specified pickup time, then this could happen. Again, API will behave the same as UI.
- No Uber Pool support. There's no way to predict the avaiability of Uber pool in the future. In the future, there could do a Uber Pool/UberX combo option though.

#### Future Features
- Uber Pool/ Uber X combo.
- Uber eats.
- Better Surge handling.
- Better exception handling.
- Trip branding.
- Webhook on status changed.
- smart suggest pick up time based on desstination.

### Users

| Industry | Example Customer | Description |Details|
| --- | --- | --- | --- |
|Smart Home| Amazon Echo, Google home| Schedule a ride for the future with a simple voice command or based on conversation|Details|
|Personal Assistant| Siri, Google | |Details|
|Social| Messenger, iMessage | |Details|
|Airlines| Delta | |Details|
|Restuarnts, event venues, movies| Open Table | |Details|
|Commute| Outlook | |Details|
|Event Organizer| Enterprise | |Details|

### API Design
#### [Endpoints](../APIDesign/endpoints) 

### Metrics

### Go To Market
