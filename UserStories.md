# Find food Trucks in San Francisco -- Core User Stories

All User Stories include front end + back end work.

1)  **User Registration**: As a User, I want to be able to register on
    the mobile app using my phone number.

    a.  **Technical Change**: Present a login screen to the user to
        register using the phone number.

    b.  **Acceptance Criteria**: The entered user details are stored in
        the Database. The user does not have to login again unless the
        app is re-installed. OP Time: <= 1 sec **Bonus**: Verify the user by sending a
        1-time SMS code. \[Outside of scope for MVP\]

    c.  **Dependencies**: API and Database modules.

    d.  **Priority**: Critical

    e.  **Sub-Tasks:**

        i.  **Front End:** Registration UI for iOS and Android phones
            and validation of phone number \[Just regex validation for MVP\]

        ii. **API**: Interaction with User Service to "register" the
            user.

2)  **Search**: As a User, I want to be able to search for closest local
    food trucks based on my location.

    a.  **Technical Change**: The App's home page must show the closest
        food trucks to the user's current location.

    b.  **Acceptance Criteria**: Search results displayed as a "List"
        and must be based on user's cuisine preferences, user's minimum
        food truck rating, exclude past ordered cuisines in the last X
        days \[X is configured as a server-side value\] and user's
        search radius. If no food trucks are found outside of the last X
        days user's cuisines, fall back to users' preferences, rating
        and search radius.  OP Time: <= 2 secs.
	 **Bonus**: Ability to expand the search
        radius if users preferred food truck is not in the initial list
        displayed. \[Outside of scope for MVP\]

    c.  **Dependencies**: API and Database modules.

    d.  **Priority**: Critical

    e.  **Sub-Tasks:**

        i.  **Front End:** Home Page screen for rendering the results
            based on user's location

        ii. **API:** Accepts UserId and location and calls the "Search
            Service" for results. Search service calls "Recommendation
            Service" for filtering based on Users Preferences. Search
            service gets food trucks closest to the user and collates
            the results.

3)  **Settings:** As a user, I want to store my preferences in a
    persistent database so that they will be used in the search results.

    a.  **Technical Change**: The App's must present a "settings" page
        to the user to record users preferred search radius, minimum
        star rating for food truck search, preferred cuisines.

    b.  **Acceptance Criteria**: User will be able to save preferred
        search radius, minimum star rating for food truck search,
        preferred cuisines in a database.  OP Time: <= 1 sec 
	**Bonus**: User can assign "ranking" to the cuisine preferences. 
        The search result list will be ordered by distance + preferred 
	cuisine ranking. \[Outside of scope for MVP\]

    c.  **Dependencies**: API and Database modules.

    d.  **Priority**: Critical

    e.  **Sub-Tasks**

        i.  **Front End:** A screen for accepting user preferences for
            Search Radius, Cuisine Preference and Minimum star rating.

        ii. **API:** Accepts the user preferences and stores them.

4)  **Save and Rate Visited food truck:** As a user, I want to be able
    to "save" the food truck I visited and rate it.

    a.  **Technical Change**: The app must allow the user "save" a food
        truck location as "visited" on a given date and also let the
        user "rate" the food truck.

    b.  **Acceptance Criteria**: User will be able to save the app
        rating and date on which he/she visited. This is stored in the
        database and used by "Recommendation Service".  OP Time: <= 1 sec

    c.  **Dependencies**: API and Database modules.

    d.  **Priority**: High \[App will still function even if this user
        story is not done for version 1 but is included as part of
        Version 1\]

    e.  **Sub**-**Tasks:**

        i.  **Front End:** UI for accepting food truck rating and data
            visited

        ii. **API:** Record food truck rating and visit date. \[The
            visit date will be used by recommendation service when
            filtering out recently visited food trucks\]

5)  **Security:** As a stakeholder, the system must be secure from
    various forms of cyber-attacks.

    a.  **Technical Change:** Allow secure sessions \[STS/token
        service\] so that only authorized users are allowed to call the
        API. Also, API layer must hosted on SSL

    b.  **Acceptance Criteria:** Users with an invalid or missing token
        will not be allowed to call the API layer.

    c.  **Dependencies:** API call to generate tokens.

    d.  **Priority:** Critical

6)  **Backend Job:** Maintain the San Francisco city data in a DB and sync with
    master DB \[from City of SFO\] every night updating only the changed
    values.

    a.  **Technical Change:** Create a batch job to sync changes from
        master DB into local DB

    b.  **Acceptance Criteria:** Only the changes values must be synced.
        Deletes must be deleted on the local DB. OP Time: <= 1 Minute

    c.  **Dependencies:** User, Search and Recommendation services

    d.  **Priority:** Critical.


**Note: I would also link the "Test Cases" to the User Stories.**
