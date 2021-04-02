folder structure:

Todo-list Submission
│
│# Project File  
│──gtd
│	├───project
│	│   ├───static
│	│   │   ├───css
│	│   │   └───images
│	│   ├───templates
│	│   │   └───registration
│	│   ├───todo
│	│   │   ├───data
│	│   │   ├───mail
│	│   │   │   ├───consumers
│	│   │   │   └───producers
│	│   │   ├───management
│	│   │   │   └───commands
│	│   │   ├───migrations
│	│   │   ├───operations
│	│   │   ├───static
│	│   │   │   └───todo
│	│   │   │       ├───css
│	│   │   │       └───js
│	│   │   ├───templates
│	│   │   │   └───todo
│	│   │   │       ├───email
│	│   │   │       └───include
│	│   │   ├───tests
│	│   │   │   └───data
│	│   │   └───views
│	│   └───__pycache__
│	└───staticfiles
│
│  
│# Virtual Environment File:
├env_submission
│	├───Scripts
│	│   ├───activate
│	├───Include
│	├───Lib
│	├───Src

Running the website on a localhost:
 
Step 1: Activate virtual environment - "env_submission\scripts\activate"
Navigate to folder "Todo-list_Submission" 

Step 2:  "Todo-list_Submission"  navigate folder "gtd" - In Anaconda prompt

execute the command "python manage.py runserver --settings=project.local"

Step 3: open in browser :
admin : 127.0.0.1:8000/admin   (staffer)
user : 127.0.0.1:8000 (user1/user2)


Detailed process of setting up website:
---------------------------------------
Step 1:Create virtual environment: "python -m venv env_submission" which creates a virtual environment folder "env_submission" say "c:\env_submission"

Step 2: Activate virtual environment: "env_submission\Scripts\activate"
activates virtual environment

Step 3: execute these commands as part of installation of project:

"pip install django",
"pip install django_extensions",
"pip install bleach",
"pip install pipenv" 

Step 4: execute "gh repo clone shacker/gtd" for cloning with the necessary files for the project

Step 5: modify DATABASES in local.example.py to 
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
and replace the file name from "project.local.py" to "project.py"

Step 6: delete the file "pipfile.lock" and run "pipenv install --dev" in command prompt

Step 7: execute 
"python manage.py migrate --settings=project.local", 
"python manage.py migrate todo --settings=project.local", 

Step 8:
loading of data to database:
"python manage.py hopper --settings=project.local" 

Step 9: for creating admin user execute 
"python manage.py createsuperuser --settings=project.local" 

step 10: for running the website in localhost execute 
"python manage.py runserver --settings=project.local" 

Credits for making the project:
Took support of "https://github.com/shacker/django-todo.git" repository for building the project


