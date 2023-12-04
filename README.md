## Contact:
#### davidfrance475@gmail.com
#### 702-373-8115


Put an introduction paragraph here

#### Contents
1. [Files](#files)
2. [Code Review](#code-review)
3. [Software Engineering and Design](#software-engineering-and-design)
4. [Data Structures and Algorihtms](#data-structures-and-algorithms)
5. [Databases](#databases)
6. [Professional Assessment](#professional-assessment)

## Files

##### Files prior to enchancement: 
[Grazioso Salvare Dashboar](https://github.com/dfrance2010/CS499/blob/Original/CS340_project2_dashboard.ipynb)  
[animalshelter.py](https://github.com/dfrance2010/CS499/blob/Original/animalshelter.py) 

##### Files after enhancement:
[animalshelter.py](https://github.com/dfrance2010/CS499/blob/Final/animalshelter.py)  
[dash_css.py](https://github.com/dfrance2010/CS499/blob/Final/dash_css.py)  
[Grazioso Salvare Dashboard](https://github.com/dfrance2010/CS499/blob/Final/grazioso_salvare_dashboard.ipynb)

## Code Review 


Youtube video covering my code review prior to adding enhancements for my CS-499 final project:  
<iframe width="560" height="315" src="https://www.youtube.com/embed/76tEqNTcvFA?si=nYg4x87zR1OLd5L2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>  
[Back to the top](#contents)

## Software Engineering and Design 


For this enhancement, I created the following components:  
**Added login/logout** 
This is a security feature to ensure only valid users can access the database and only users with read/write permission can perform create/update/delete operations.   
    1. Added input and login/logout buttons to the dashboard.
    2. Created ‘Users’ collection in database.
    3. Used hashlib library to add in username/password pairs and their associated read/write permissions. Strings are hashed using hashlib’s SHA-256 algorithm.
    4. Added check_user() and method to animalshelter.py to check if user has permission to login.
    5. Added check_permission() method to animalshelter.py to check a user’s read/write permission to access ‘Advanced Options’.
    6. Added login and logout callbacks in grazioso_salvare_dashboard.ipynb.
#### **Added ‘Show Advanced Options’ and ‘Delete Animal’ buttons**
This was the first step in adding all CRUD functionality to the dashboard.  
    1. Created buttons for the dashboard with associated callbacks.
    2. If user has permission, ‘Show Advanced Options’ turns to ‘Hide Advanced Options’ and advanced options are shown. If they don’t have permission a message is shown.
#### **Added dropdown filters for refining the data in the view**
This allows users to better interact with the data and find what they are looking for.  
    1. Added and aligned dropdowns.
    2. Added callback to filter the data based on the selections.

Video review of enhancements and code:
<iframe width="560" height="315" src="https://www.youtube.com/embed/3_wODRyI810?si=kqjH7rnyJo2qPTV7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

These enhancements helped me to meet the following course outcomes:  
**Use well-founded techniques, skills, and tools for implementing computing solutions that deliver value and accomplish industry-specific goals**  
**Develop a security mindset to mitigate design flaws and ensure privacy and enhanced security of data and resources**  
**Build collaborative environments that enable diverse audiences to support orginazational decision making**  
**Design, develop, and deliver profesional-quality communication**

[Back to the top](#contents)

## Data Structures and Algorithms


**Improved initial load time** – I updated the initial database query to find only dogs, rather than the entire set, to populate the data table. Dogs are the focus of the business, but users can then load additional animals, or the entire set, if they like.  
**Created ‘rescue_type’ category for dogs in MongoDB** - This allows for much faster searching of the important 'Rescue Type' radio buttons.  
    * Updated existing database so all dogs that fit a rescue type would be labelled appropriately in their document.
    * Created __check_rescue_type() private method in animalshelter.py. This algorithm allows for checking any inserted or updated animals to see if they also fit a rescue type and accounts for the fact that some dogs can fit more than one rescue type.
    * Updated insert() and update() methods in animalshelter.py to check for rescue types before finalizing inserts and updates.
**Created indexes in MongoDB AAC database for the filter categories** – this was a database administrator task to make the most common queries more efficient.  

Video review of enhancements and code:
<iframe width="560" height="315" src="https://www.youtube.com/embed/Cmr1ncEY43Q?si=nEQdCey1zBf5FS15" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

[Back to the top](#contents)

## Databases 
For this enhancement, I completed the CRUD functionality of the dashboard by adding 'Create Animal' and 'Update Animal' buttons.
**Use well founded techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value:**  
    + Used data validation to ensure only quality data was being inserted/updated. 
        + Created dropdown menus with pre-selected values for ‘animal_type’, ‘breed’, ‘color’, ‘outome_subtype’, ‘outcome_type’, and ‘sex_upon_outcome’
        + Used SingleDatePicker() to ensure user has to select a date for birthdate.
        + Used geolocator to obtain ‘latitude’ and ‘longitude’ coordinates, with a map so the user can confirm their entry.
        + Created name_validation() method in animalshelter.py to ensure ‘name’ does not exceed 15 characters, and only contains letters, ‘*’, ‘-‘, or ‘ ‘ characters.  
    + Created __animal_dict() method in CS499_milestone4_dashboard.ipynb to create dictionary based on insert/update values to be passed to AnimalShelter() class. This method is used in both create_animal() and update_animal() callbacks.
    + Created private methods in animalshelter.py to fill in the fields that can be calculated.
        + __age() - returns a formatted age string in the form of ‘1 day’, ‘2 weeks’, ‘3 years’, etc. 
        + __age_in_weeks() – returns a float representing the age in weeks calculated from the provided DOB to today.
        + __next_row() – returns highest row value + 1 for newest animal.
        + __next_id() – returns the highest animal_ID value + 1.
        + __add_fields() – adds calculated fields to animal dictionary to be inserted. This ensures all fields are populated and are in the correct form for the Dash App data table.
    + Updated insert() method to add all calculated fields prior to checking if animal is a rescue type.
    + Updated update() method to check if a DOB is being updated and doing the appropriate updates if yes.
**Develop a security mindset:**  
    + Only users with read/write permissions can access the ‘Advanced Options’ on the dashboard, showing the use of the principle of least privilege. 
    + Data validation protects against injection attacks.
**Building collaborative environments:**  
    + Creating a dashboard with complete CRUD functionality allows for all team members of Grazioso Salvare to work with the most up-to-date information available from the database.
    + ‘Advanced Option’ are only shown when read/write users click on the ‘Show Advanced Option’ button. This declutters the view for those just using the read functionality of the dashboard. Further, only one ‘delete’, ‘insert’, or ‘update’ view is available at a time, based on the selected radio button.
    + Ensured to comment the code and use descriptive naming to make it easier for other developers to work with my code.
**Professional communication:**  
    + Use of bullets and screencast in narrative to clearly highlight enhancement using both written and oral/visual techniques


[Back to the top](#contents)

## Professional Assessment 


Put the professsional assessment stuff here

[Back to the top](#contents)
