## David France
**Contact:**<br>
davidfrance475@gmail.com  
702-373-8115


This page hosts my work for the CS-499 capstone project. This project helps demonstrate the computer science technical skills I’ve developed at SNHU. In addition to coursework, my 20 years of high-end experience in the casino and restaurant industries have helped me develop the ability to collaborate in a team environment and communicate to stakeholders. My coursework for this program also demonstrates my ability to take responsibility and hit deadlines in a remote environment. 
<br>
For this project we had to do three enhancements on previous work, covering the following categories:
<br>
1.	Software design and engineering
2.	Algorithms and data structure
3.	Databases
<br>

I chose to do all three enhancements on the same artifact – a dashboard for the fictional company, Grazioso Salvare, that allows their team members to interact with the Austin Animal Shelter database. This database holds information on a variety of animals in their system. At the top of the page, you will see the code files pre and post-enhancements. This is followed by a code review prior to starting the work, then the details for each enhancement. For each enhancement, I will go over what changes I made and how those changes helped me meet the following course outcomes:
<br>

1. Employ strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science 
2. Design, develop, and deliver professional-quality oral, written, and visual communications that are coherent, technically sound, and appropriately adapted to specific audiences and contexts 
3. Design and evaluate computing solutions that solve a given problem using algorithmic principles and computer science practices and standards appropriate to its solution, while managing the trade-offs involved in design choices (data structures and algorithms) 
4. Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals (software engineering/design/database) 
5. Develop a security mindset that anticipates adversarial exploits in software architecture and designs to expose potential vulnerabilities, mitigate design flaws, and ensure privacy and enhanced security of data and resources
<br>


Following that, I have a video showcasing the changes in the dashboard, along with a quick review of the code. Closing out each section will be a short reflection on what I learned and what challenges I faced in completing the enhancement.


### Contents
1. [Files](#files)
2. [Code Review](#code-review)
3. [Software Engineering and Design](#software-engineering-and-design)
4. [Data Structures and Algorihtms](#data-structures-and-algorithms)
5. [Databases](#databases)
6. [Professional Assessment](#professional-assessment)

# Files
Each enhancement was performed on the same artifact. Here are the original code files, followed by the files after all enhancements. Each section goes over what I specifically changed for that enhancement.

**Files prior to enchancement:**<br> 

[animalshelter.py](https://github.com/dfrance2010/CS499/blob/Original/animalshelter.py)   
[Grazioso Salvare Dashboard](https://github.com/dfrance2010/CS499/blob/Original/CS340_project2_dashboard.ipynb)  

**Files after enhancement:**<br> 

[animalshelter.py](https://github.com/dfrance2010/CS499/blob/Final/animalshelter.py)  
[dash_css.py](https://github.com/dfrance2010/CS499/blob/Final/dash_css.py)  
[Grazioso Salvare Dashboard](https://github.com/dfrance2010/CS499/blob/Final/grazioso_salvare_dashboard.ipynb)

# Code Review 


Youtube video covering my code review prior to adding enhancements for my CS-499 final project:  

<iframe width="560" height="315" src="https://www.youtube.com/embed/76tEqNTcvFA?si=nYg4x87zR1OLd5L2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>  
[Back to the top](#contents)

# Software Engineering and Design 


For this enhancement, I added a login/logout section, dropdown filters for refining the data in the view, and an 'Advanced Options' section with a 'Delete Animal' button. This all works towards improving the use and functionality of the dashboard for the Grazioso Salvare team. Key elements included creating MongoDB collections for users and salt values, then inserting qualified users and their associated read/write permissions by first salting, then hashing the strings. The login and advanced options also included creating check_user() and check_permission() methods in animalshelter.py for security checks. Finally, an backup database was created to hold deleted animals in to save inattentive users from their mistakes. This enhancement helped me to meet the following course outcomes:


**Use well-founded techniques, skills, and tools for implementing computing solutions that deliver value and accomplish industry-specific goals**<br>

  + Added input and login/logout buttons to the dashboard.
  + Created ‘Users’ collection in database.
  + Used hashlib library to add in username/password pairs and their associated read/write permissions. Strings are hashed using hashlib’s SHA-256 algorithm.
  + Added check_user() and method to animalshelter.py to check if user has permission to login.
  + Added check_permission() method to animalshelter.py to check a user’s read/write permission to access ‘Advanced Options’.
  + Added login and logout callbacks in grazioso_salvare_dashboard.ipynb. 

**Develop a security mindset to mitigate design flaws and ensure privacy and enhanced security of data and resources**<br>  

+ Principle of least privilege means only users with read/write access can make changes to the database.
+ Salting and hashing username/password pairs protects the stored values even if they are accessed.
+ Creating methods for checking users and permissions prevents unauthorized access.
    
**Build collaborative environments that enable diverse audiences to support orginazational decision making**<br>

  + Improved functionality of dashboard means Grazioso Salvare employees can better do their jobs.
  + Improved comments and naming conventions in code so anyone can jump in and know what is going on.

**Design, develop, and deliver profesional-quality communication**<br>

  + Created written and video narratives to communicate changes.

Video review of enhancements and code:
<iframe width="560" height="315" src="https://www.youtube.com/embed/3_wODRyI810?si=kqjH7rnyJo2qPTV7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


[Back to the top](#contents)

# Data Structures and Algorithms


**Improved initial load time** 

I updated the initial database query to find only dogs, rather than the entire set, to populate the data table. Dogs are the focus of the business, but users can then load additional animals, or the entire set, if they like.  


**Created ‘rescue_type’ category for dogs in MongoDB** - This allows for much faster searching of the important 'Rescue Type' radio buttons.  

   * Updated existing database so all dogs that fit a rescue type would be labelled appropriately in their document.
   * Created __check_rescue_type() private method in animalshelter.py. This algorithm allows for checking any inserted or updated animals to see if they also fit a rescue type and accounts for the fact that some dogs can fit more than one rescue type.
   * Updated insert() and update() methods in animalshelter.py to check for rescue types before finalizing inserts and updates.
    
**Created indexes in MongoDB AAC database for the filter categories** – this was a database administrator task to make the most common queries more efficient.  

Video review of enhancements and code:
<iframe width="560" height="315" src="https://www.youtube.com/embed/Cmr1ncEY43Q?si=nEQdCey1zBf5FS15" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

[Back to the top](#contents)

# Databases 
For this enhancement, I completed the CRUD functionality of the dashboard by adding 'Create Animal' and 'Update Animal' buttons.


**Use well founded techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value:**<br> 
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
  
   
**Develop a security mindset:**<br>  
+ Only users with read/write permissions can access the ‘Advanced Options’ on the dashboard, showing the use of the principle of least privilege. 
+ Data validation protects against injection attacks.
 
**Building collaborative environments:**<br>
+ Creating a dashboard with complete CRUD functionality allows for all team members of Grazioso Salvare to work with the most up-to-date information available from the database.
+ ‘Advanced Option’ are only shown when read/write users click on the ‘Show Advanced Option’ button. This declutters the view for those just using the read functionality of the dashboard. Further, only one ‘delete’, ‘insert’, or ‘update’ view is available at a time, based on the selected radio button.
+ Ensured to comment the code and use descriptive naming to make it easier for other developers to work with my code.

    
**Professional communication:**<br>  
  + Use of bullets and screencast in narrative to clearly highlight enhancement using both written and oral/visual techniques


[Back to the top](#contents)

# Professional Assessment 


Put the professsional assessment stuff here

[Back to the top](#contents)
