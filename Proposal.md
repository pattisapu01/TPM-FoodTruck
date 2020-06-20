# Find food Trucks in San Francisco -- Project Proposal__**

**Scope**: The project proposal is for the creation of a mobile app that
finds various food truck operators belonging to different cuisines
within a certain radius of the user's location. The app must suggest
"new" places to eat. This means, it needs to keep track of what places
the user has eaten previously and give recommendations "outside" of the
recently eaten places but within the user's cuisine preferences.

**Deliverables:** A mobile application that talks to API layer to fetch 
Food Truck operators that are closet to the user's location. 
The "Recommendation Engine" must take into
account the recent ordered \[Past X Days\] food trucks and try to filter
them out so that "new" food trucks can be recommended. Another criterion
is "Food Truck" rating. Food truck search radius, cuisine preferences,
number of food trucks to retrieve and minimum food truck rating are
configurable via a settings page in the app

**Constraints**: A) Users allows their current location to be read by
the App. B) The truck database is always available. C) The mobile app
will work on iOS and Android.

**Assumptions:** A) Users current location can be read by the app. B)
Users will "save" the food truck they visited on a given day. \[This
data will help the "Recommendation Service"\]. C) Users have their
favorite cuisines saved in profile settings. D) Users register with the
app using their phone number \[Phone number will be their unique
Identifier\], E) The app must respond to the users "closest food truck"
request within 2 seconds. F) Ordering food from mobile app is out of
scope for MVP.

**Risks:** The project is dependent on data supplied by City of San
Francisco. If this data is not available, the app would not be
functional. To mitigate this risk, we may develop our own backend to
load a one-time dump of all food truck operators. From San Francisco's
API. This solution will need incremental updates from the source data
set.

**High Level Requirements:**

-   **Actors:** **Users** searching for food trucks \[Food truck Vendors
    are not actors as they don't interact with our system directly\]

-   **Mobile App:** A Mobile app that registers users, stores the user's
    preferences, lists the closest food trucks based on user's location
    taking in to account where the user has ordered from over the last X
    days, Mark a food truck as "ordered" with timestamp. This will feed
    the recommendation service. A food truck can also be rated.

-   **Backend:** API services to process the above user actions from the
    front end. \[User Service, Search Service, Recommendation Service\]

-   **Jobs:** A daily job that refreshes the local database with the
    data from San Francisco.

-   **Database:** A database to store user data, user's past food truck
    orders, the dataset of all food trucks from San Francisco

**Timelines:** The project will take 4 weeks to complete. 2 weeks for
Backend \[Including Scheduled Job\], 1 week for front end and 1 week for
testing. Front end and backend can start in parallel. Backend can use
mock data to simulate calls from front end.

**Resources:** This project requires 3 resources. 1 Front end Engineer
experienced in iOS and Android, 1 middle tier \[REST API\] and DB
engineer and 1 QA tester. QA tester is required only for 1 week.
