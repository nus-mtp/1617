## Functional Requirements

* The user shall be able to register a new account and log in to the system.
* The user shall be able to search the arrival time of trains for a particular
* station.
* The system should be able to calculate and display the shortest path, and the
* estimated travel time, from the starting point to the destination point,
* taking into account the bus/MRT timing and traffic conditions reported by the
* users at real time.
* The system shall provide voice alert to the user if the train he is trying to
* catch has left the station.
* The system should be able to collect data on traffic conditions posted by
* users, and display them on the map of the app. 
* The system should also allow users to rate the accuracy of this information at
* this point of time, and remove outdated/inaccurate information automatically.
* The user shall be able to know whether a particular bus/MRT or bus stop/MRT
* station is crowded. The user will be able to look for this information (in
* form of text or images) in the app.
* The user shall be able to request other users to provide information for them
* about the crowd information on the relevant bus/MRT or bus stop/MRT station.
* The user shall be able to rate whether a source of information provided by
* other users is useful or not.
* The user shall be able to provide information about the crowdedness of a place
* by himself.
* The user shall be able to provide information about the crowdedness of a place
* upon
 request from other users.
 * The system shall have a route tracking function. In this function, each bus
 * stop/MRT station
  is represented by a circle. At the beginning of his travel, all circles in his
  route are colored red. Once the bus/MRT passes a bus stop/MRT station, the
  circle representing the bus stop/MRT station will be colored green. Therefore,
  user can know when to get off the bus/MRT.
  * The system shall allow addition of new bus/MRT information, including the
  * routes of the bus/MRT, name and number of the stops/stations through its
  * travel path, the time interval between two consecutive buses/MRTs, the time
  * for earliest/ latest bus/MRT for user who has a unique identity of
  * administrator.
  * The system shall allow update of existed data of bus/MRT information,
  * including the routes of the bus/MRT, name and number of the stops/stations
  * through its travel path, the time interval between two consecutive
  * buses/MRTs, the time for earliest/ latest bus/MRT for user who has a unique
  * identity of administrator.
  * The system shall allow user who has a unique identity of administrator to
  * browse all the comments/posts in the database from ordinary users, and allow
  * him to delete improper or obsolete comments/posts.
  * The system shall allow administrators to check through all accounts of
  * ordinary users, and shall allow administrators to delete malicious accounts
  * or zombie users.

## Non-functional requirements

* **Accessibility** The system should be accessible to as many people as
* possible. People with weak vision should be accessible to the system with aid
* of voice guides and notifications.
* **Availability** The system should be available for any time when the bus/MRT
* system is working.
* **Capacity (current and forecast)**
 Currently, the system should be capable to handle traffic information from all
 buses and MRTs in Singapore. From the view of long-term development, the
 following versions might also include information from other cities.
 * **Compliance** The use of data and dissemination of traffic information in
 * our system should follow local policies and legislations in Singapore
 * strictly.
 * **Extensibility** The system should have a good support for extensions.
 * Improvement of existed functions and addition of new features shall be
 * supported. In the next major version upgrade the system should also include
 * customizations in terms of UI and functions.
 * **Maintainability** The maintenance of the system should be simple and
 * straightforward. The database should have elegant structures to increase the
 * maintainability of the system. The system should also have limitations on
 * user’s posts to make maintenance easier.
 * **Performance** The system should have a reasonably quick response to user’s
 * operations. The system should have relatively low occupation of device’s CPU
 * and memory.  Additionally, the system should also have an effective method to
 * retrieve online data to shorten the waiting time for users to see the results
 * of their requests.
 * **Platform compatibility** This system should be compatible on any of Android
 * Platform 4.x versions.
 * **Pricing** This system should be a free application for any Android 4.x
 * devices.
 * **Reliability** The system should regularly keep information updated and
 * reliable.
 * **Security** The system should have enough protections for user accounts. The
 * system should defend the database from malicious SQL injections and other
 * types of attacks.
 * **Stability** The system should keep its stability on Android devices. It
 * should be working without frequent crashes or break-down.
 * **Usability by target user community** The system should have a user-friendly
 * UI and be easily used by our target users. The operations and the
 * presentation of information should be simple and neat.
