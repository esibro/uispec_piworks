# UI Spec - User Management Screen

This User Interface Specification describes required functionalities and behaviour of a user management screen. The UI looks like this:

![User Interface](/userinterface.png)

The interface consists of three parts (as you can see on the image):

- Header Section (Section 1)
- Form Section (Section 2)
- List Section (Section 3)

![User Interface](/sections.png)

###### Note:
For better performance and speed I would recommend to program a kind of SPA (single page application), so **just the required/renewed parts should reload and not the whole page.**

## General Requirements
These are the essential requirements of the system and the general logic behind it:
1. create new user
2. fill out form
3. save user
4. show saved user in list

More detailed requirements will be described down below.

---

## Start
The user should see following sections at the beginning, when opening the screen:
- Section 1 is fully visible
- Section 2 is plain white area
- Section 3 is also fully visible, only contains data if user were saved before (check database)

-----

## Content, functionalities and behaviour
### Section 1

This section consists of three components: two buttons and one checkbox
##### Button #1 
Button #1 called 'New User'

###### CSS:
- Background-color: #147db7

###### Functionalities, Behaviour:
- displays section 2, section 2 is not visible until clicked on Button #1
- enables the user to fill information

##### Button #2 
Button #2 called 'Save User'

###### CSS:
- Background-color: #147db7 (when enabled)
- Background-color: #b7d6e5 (when disabled)

###### Functionalities, Behaviour:
- button is disabled until form input fields are completely filled out
- if clicked and input is invalid (description down below), pop-up window with error description
- if clicked and input valid, displays the new user in the table (section 3)

##### Checkbox
**Label** 'Hide Disabled User'
If checkbox enabled, user who are marked as disabled won't be visible in the list 

------

### Section 2

**Components:** Header 'New User', Form consisting of four text input fields, one dropdown menu, one checkbox

##### Input Fields
1. Username: String input field
2. Display Name: String input field - not visible in the table but still saved in database for other purposes
3. Phone: String input field, non-valid if contains letters, only digits
4. Email: String input field, check if really e-mail, othervise non-valid

##### Dropdown Menu
**Label** 'User Roles' with three options:
1. Guest
2. Admin
3. SuperAdmin 

**Placeholder:** 'Select user role..'

##### Checkbox
**Label** 'Enabled' 
if checked = true
not checked = false

---

### Section 3
**Components**: Table with four columns, data can be **filtered** ascending, descending by number or alphabetically:
1. ID: User get sequentially an ID assigned, happens automatically when user is saved
2. User Name: Username input comes here
3. Email: Email input comes here
4. Enabled: if enabled box checked: true, else false

Even rows get a background-color: #b7d6e5

