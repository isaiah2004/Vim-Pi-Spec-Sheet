# Sub-task 4: Implement a Drive sync feature

#### Objective:

Implement a Drive Sync shortcut for the code base in the current app. Add a configuration and Authentication system to allow user to easily sync. The sync must run automatically in background on save. Ensure to use the google O-auth and Google drive API library provided by google.

#### Requirements:

1. Install the API libraries for python
	1. Install the google auth library
	2. Install the google drive library
2. Implement a configuration system which get O-Auth and finishes user folder configuration
3. Implement a shortcut to configure Drive sync and turn it on and off
4. Implement a function to give folder state
5. Implement a function to get drive state
6. Implement a function to compare the remote and local states and make the necessary changes when a file save is detected.

---

#### Instructions:

1. Ensure the code is written modularly. Implement the Program in a new file called `synchronize.py.`
2. At this point make sure the code is written following all conventions.
3. The state must sync automatically every minute.
4. The user should able to turn sync off.


