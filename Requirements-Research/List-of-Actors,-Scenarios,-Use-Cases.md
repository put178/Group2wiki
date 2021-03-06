This is a page for brainstorming:

● List of Actors, Scenarios, and Use Cases

○ Including proper supporting descriptions for each

from the Milestone 1 requirements document.

## Actors

### Standard User
- a user who is able to complete typing challenges
- may view their own typing progress through stored user metrics
- interact with user group(s)
- interacts with Firebase SDK (user will create a username and password for authentication)

### Administrative User
- a user who can manage other users and view their typing progress
- manage user groups
- may assign typing challenges to standard users or user groups
- also can do everything that a standard user is able to do

### Super Administrative User
- manage Administrators
   - create groups and assign an administrator to manage the group
   - add and remove administrators
- also can do everything that a standard user and administrator can do


### Firebase SDK
- interacts with our software through API calls
- manages user authentication, user permissions/user groups, store user data in cloud database, store user data

### Other APIs possibly!
//TODO: decide on the format for our tests (this will narrow down our choice in text fetching APIs)


## Scenarios
//TODO: Flesh out with actual steps, add more scenarios

### (Special Note: Every permission given to an Administrator will also be given to a Super-Administrator)

### 01: Users can Login
- The User can login through the firebase API
### 02: Users can selects the Mode
- The user can choose between Standard, Programmer, and Dictation mode
### 03: User views their typing test results
- The user can see all of their information from prior test and other metrics like wpm etc...
### 04: User shares their typing test results
- The User can share there challenge results with other users
### 05: User can view leaderboards
- The User can access a leaderboard with other users for an assigned challenge 
### 06: Administrator can create and manage groups
- The administrator can create groups and invite or delete users from a group
### 07: Administrator can assign typing challenges and look at the results
- 
### 08: Users can take assigned tests
- 
### 09: Super-Administrator can create and manage Administrators
- A super Admin can make a standard user an Admin User


### ? API takes longer than 10 seconds (??) to respond to request for data
### ? User selects character combinations to focus on (??)
### ? User wants to pause the typing test and resume, restart or quit later
### ? Turn off the background music (??)

## Use Cases

### Use Case ID: 0
### Use Case
- User logs in
### Primary Actor(s)
- Every type of user (Standard, Admin, Super-Admin)
- Firebase (authentication)
### Preconditions
- User has a user account
### Basic Flow
1. user starts software and arrives at login screen
2. user click on username input box
3. user enters in username
4. user clicks on password box
5. user enters in password
6. user presses enter
7. firebase authentication responds
### Alternative Flow
6a) User enters in wrong username or password
   - a1) User is notified that something is wrong and they need to reenter
   - a2) User is given the option to pick a new username or password (with the correct verification)
   - a3) back to step 6.

6c) user does not have internet connection
   - c1) user given notice to connect to internet

7a) firebase doesnt respond in time

---

### Use Case ID: 1
### Use Case
- user starts a typing challenge in programmer mode
### Primary Actor(s)
- every type of user
- firebase
### Preconditions
- user is logged in and authenticated
- user has internet connection
### Basic Flow
1. after the user has logged in, a dashboard will be displayed
2. the user clicks on the programming tab.
3. next the user will be able to select the programming language and the duration of the challenge (the challenge's options are TBD)
4. once the user is ready, they press the start button
5. the challenge will begin with the duration and programming language of the users choice
6. the users stats from the challenge will be uploaded to the firebase db
### Alternative Flow
2a) the ui and design stage will influence the order of these steps

---

### Use Case ID: 2
### Use Case
- user starts a typing challenge in normal mode
### Primary Actor(s)
- any type of user
- firebase
### Preconditions
-user is logged in and authenticated
-user has an internet connection
### Basic Flow
1. after the user has logged in, a dashboard will be displayed
2. user clicks on normal typing mode
3. user will be able to adjust the typing challenge (TBD), and the duration of the typing challenge.
4. once the user is ready, they press the start button
5. the challenge will begin with adjustments the user made in step 3
6. the users stats from the challenge will be uploaded to the firebase db
### Alternative Flow
2a) the dashboard will be designed in stage 2

---

### Use Case ID: 3
### Use Case
- user checks their typing stats
### Primary Actor(s)
- every type of user
- firebase
### Preconditions
- user is logged in and authenticated
- has an internet connection
### Basic Flow
1. After logging in, the user will be displayed a dashboard
2. Somewhere on the dashboard (TBD) the users stats will be displayed, with a button
to pull up more stats on page just for stats
### Alternative Flow
2a) the dashboard will be designed in stage 2

---

### Use Case ID: 4
### Use Case
- admin adds user to their group
### Primary Actor(s)
- admin user (super admin in the same domain)
### Preconditions
- admin has control of the group
- the user the admin wants to add to the group must exist and be in the domain
### Basic Flow
1. Once the admin logs in, they will be directed to the main dashboard.
2. When a user gets to the main dashboard, if they have admin persmissions, a manage groups page will be present
3. Admin clicks on manage groups page
4. admin selects the group the want to manage
5. admin clicks add new member
6. a list of users in the domain will appear
7. the admin clicks on the user they want to add and presses add
### Alternative Flow

---

### Use Case ID: 5
### Use Case
- user begins an audio to text test (name TBD)
### Primary Actor(s)
- every type of user
### Preconditions
- user is logged in and authenticated
### Basic Flow
1. from the dashboard, the user will click on the audio to text tab
2. this will lead to a new page where the user can adjust the speed of the audio
3. after adjusted the audio to text test, the user can press the start button
4. one-by-one, words will begin being read out loud, and the user has to type the words before the next one pops up
5. after the test is done, the user will be notified of there typing stats
### Alternative Flow

4a. user types word wrong
   - a1) user will be notified by a visual or sound effect
   - a2) user can continue to the next word


---

### Use Case ID: 6
### Use Case
- admin assigns typing challenges to group
### Primary Actor(s)
- admin user
### Preconditions
- the admin is assigning a typing challenge to a group that they created or were given permissions to
### Basic Flow
1. from the dashboard, the admin will click on the manage groups tab
2. next, admin clicks on the group they want to manage
3. the admin will be able to pick a typing challenge, and edit the typing challenge with options such as duration and difficulty
4. the admin clicks a date/time which the typing challenge is to be completed by
5. the admin will click the submit button and the task will be sent to the group
### Alternative Flow

---

### Use Case ID: 7
### Use Case
- admin creates a new group
### Primary Actor(s)
- admin user
### Preconditions
### Basic Flow
1. from the dashboard, the admin will click on the manage groups tab
2. from the manage groups page, the admin will be able to add a new group
3. the admin will first give the group a name, then press submit
### Alternative Flow

---

### Use Case ID: 8
### Use Case
- admin deletes a group
### Primary Actor(s)
- admin user
### Preconditions
### Basic Flow
1. from the dashboard, the admin will click on the manage groups tab
2. from the manage groups page, the admin will be able to see each of their groups
3. user selects the delete button on the group they wish to delete
4. admin will be given a popup menu to double-check if the admin wants to delete the group
5. if the admin clicks yes, the group will be deleted
### Alternative Flow


---

### Use Case ID: 9
### Use Case
- user attempts a certain group's assigned typing challenge
### Primary Actor(s)
- user of a certain group (ex: group A)
### Preconditions
- user has been invited to group A and has accepted the invite
- admin has sent out a task for group A
### Basic Flow
1. from main dashboard, user clicks on groups pop down menu
2. user clicks on group A
3. under challenges, user clicks on the challenge to be completed
4. user completes the challenge
5. admin is notified that a user in their group has completed the challenge
### Alternative Flow

---

### Use Case ID: 10
### Use Case
- super admin creates a new admin
### Primary Actor(s)
- super admin
### Preconditions
-the user that the super admin wants to give admin persmissions to exists
### Basic Flow
1. somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin
permissions
2. if the super admins clicks it, a list of users that the super admin had previously assigned to be admin will be shown
3. the super admin will be able to click on the add new button
4. after pressing the add new button, the super admin can type the unique identifier of the user they want to assign admin permissions
5. after the super admin presses submit, the user that was assigned to be an admin will be notified
### Alternative Flow

---

### Use Case ID: 11
### Use Case
- super admin removes an admins permissions
### Primary Actor(s)
- super admin
### Preconditions
-the admin that the super admin wants to demote exists
### Basic Flow
1. somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin
permissions
2. if the super admins clicks it, a list of users that the super admin had previously assigned to be admin will be shown
3. the super admin selects the admin that they want to remove
4. after select the user and press remove, the super admin will be given an extra popup to make sure that the super admin chose the correct admin
5. after the super admin presses submit, the admin that was removed will be notified
### Alternative Flow

---

### Use Case ID: 12
### Use Case
- super admin adds a user to their domain
### Primary Actor(s)
- super admin
### Preconditions
-the user that the super admin wants to add must exist
### Basic Flow
1. somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin
permissions
2. after clicking on the special tab, there will be a place to manage their domain
3. the super admin presses 'add new user'
4. the super admin types the user's unique id and presses submit
5. the user will be added to the the domain
### Alternative Flow

---

### Use Case ID: 13
### Use Case
- the super admin removes a user from their domain
### Primary Actor(s)
- super admin
### Preconditions
-the user that the super admin wants to add must exist
### Basic Flow
1. somewhere on the dashboard, the super admin will have a special tab or menu that is only given to users with super admin
permissions
2. after clicking on the special tab, there will be a place to manage their domain, with a list of users in the domain
3. the user clicks on the user they want to delete and presses delete 
4. the super admin will get an extra popup assuring that they chose the correct user
5. if the super admin presses yes, the user will be deleted from the domain
### Alternative Flow
