# David France 
#### 702-373-8115
#### davidfrance475@gmail.com


Put an introduction paragraph here

#### Contents
1. [Code Review](#code-review)
2. [Software Engineering and Design](#software-engineering-and-design)
3. [Data Structures and Algorihtms](#data-structures-and-algorithms)
4. [Databases](#databases)
5. [Professional Assessment](#professional-assessment)

## Code Review 


Youtube video covering my code review prior to adding enhancements for my CS-499 final project:
<iframe width="560" height="315" src="https://www.youtube.com/embed/76tEqNTcvFA?si=nYg4x87zR1OLd5L2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
[Back to the top](#contents)

## Software Engineering and Design 


For this enhancement, I created the following components:
+	**Added login/logout** – this is a security feature to ensure only valid users can access the database and only users with read/write permission can perform create/update/delete operations.   
    * Added input and login/logout buttons to the dashboard.
    * Created ‘Users’ collection in database.
    * Used hashlib library to add in username/password pairs and their associated read/write permissions. Strings are hashed using hashlib’s SHA-256 algorithm.
    * Added check_user() and method to animalshelter.py to check if user has permission to login.
    * Added check_permission() method to animalshelter.py to check a user’s read/write permission to access ‘Advanced Options’.
    * Added login and logout callbacks in grazioso_salvare_dashboard.ipynb.
+ **Added ‘Show Advanced Options’ and ‘Delete Animal’ buttons** – this was the first step in adding all CRUD functionality to the dashboard.  
    *	Created buttons for the dashboard with associated callbacks.
    * If user has permission, ‘Show Advanced Options’ turns to ‘Hide Advanced Options’ and advanced options are shown. If they don’t have permission a message is shown.
+	**Added dropdown filters for refining the data in the view** – this allows users to better interact with the data and find what they are looking for.  
    *	Added and aligned dropdowns.
    *	Added callback to filter the data based on the selections.


These enhancements helped me to meet the following course outcomes:
1. **Use well-founded techniques, skills, and tools for implementing computing solutions that deliver value and accomplish industry-specific goals**
2. **Develop a security mindset to mitigate design flaws and ensure privacy and enhanced security of data and resources**
3. **Build collaborative environments that enable diverse audiences to support orginazational decision making**
4. **Design, develop, and deliver profesional-quality communication**

[Back to the top](#contents)

## Data Structures and Algorithms


Put the data structures and algorithms stuff here

[Back to the top](#contents)

## Databases 


Put the database stuff here

[Back to the top](#contents)

## Professional Assessment 


Put the professsional assessment stuff here

[Back to the top](#contents)
