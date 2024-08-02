# Create a Django App

Welcome to Create a Django App! After watching this video, you will be able to: Describe the Django web app structure, and create and run a simple Django web app.

Let’s look at a typical Django development process. The order of these steps may vary. 

- First, we create a **Django project** which is a container for **Django apps and settings**. Then we create and add one or more **Django apps** to the project.
- In Core Development, we create **Django models** to model the data and create views to determine which data need to be presented to the UI. We also **map the request URLs** to our views so Django can forward requests to corresponding views via URLs. Then we can start designing and building the UI. Once we are confident of the current version, we can **perform unit or system tests**. 
- After the core development is done, we need to make our Django app production-ready, using **Add-ons** such as an admin site or a 3rd party frontend library. 
- Once we have a working Django app, we can **deploy it** on a web server, either on premise or on cloud, and monitor the server status.

A Django project is essentially a Python package that contains all the settings for an instance of Django app. To create a Django project, open a command-line terminal and run: (Your current directory is `/home/project`.)

```cmd
django-admin startproject mysite
```

This initializes a Django project with related files and folders. You need to know the usage for some core files that Django creates. 

- `manage.py` is a command-line interface used to **interact with the Django project** to start the server, migrate models, and so on. 
- `settings.py` contains the **settings and configurations** for your Django project. 
- `urls.py` contains the **URL and routing definitions** of your Django app.

Once you have created the Django project container, you can add your first Django app to it. We’ll call our first app `onlinecourse`. From the `mysite` project directory, run:

```cmd
python manage.py startapp onlinecourse
```

Django will create a temporary app structure and some important app files. 

- `admin.py` includes everything you need to **create and customize an admin site** to **manage users and content**. 
- `models.py` contains the **data models and ORM**. 
- `views.py` contains **view functions and classes** to create views. 
- `urls.py` contains the **URL declarations and routing** for the app. 
- `app.py` contains the **application configuration** class. 
- The `migrations` folder contains **scripts for model migration**. 

<img src="assets/屏幕截图 2024-08-02 030918.png" alt="屏幕截图 2024-08-02 030918" style="zoom:67%;" />

Now, we add the `onlinecourse` app we just created to our `mysite` Django project. 

Open the `settings.py` file in the `mysite` folder, find the `INSTALLED_APPS list` in the settings file, and add a new entry called `onlinecourse.apps.OnlinecourseConfig` to the list. The `OnlinecourseConfig` is a configuration class that represents the `onlinecourse` app. 

Now that our app is plugged in, we can optionally set up a database for it. The `mysite/settings.py` file has a `DATABASES` dictionary to configure the databases for our app. We add a database instance by adding its connection information such as engine, name, username, and password.

Once we have set up our app and database, we can define our Django Models as the ORM component between objects and database tables. Let’s define a simple Course model here with fields like name and description. 

Next, we tell Django we’ve updated the model by running:

```cmd
python manage.py makemigrations onlinecourse
```

Django then will create migration scripts under the `migrations` folder. 

To see more details about the SQL statements for the migration, we could run:

```cmd
python manage.py sqlmigrate onlinecourse 001
```

Here, an `onlinecourse_course` table will be created.

Run:

```cmd
python manage.py migrate
```

to run the migration scripts.

Next, we create a simple view and a hard-coded html template to present the course object.

Open the `onlinecourse/views.py` file to add a `course_list` view function. It accepts an `HTTP Request` object and returns an `HttpResponse` object.

First, we get the `course` object from the database as a course object. Then, we create an html `template` and dynamically insert the course name into the placeholder. Finally, we add the completed html string as the `content` of the `HttpResponse` and return it to the UI. 

Now we associate the `course_list` view with a URL so Django will route the request URL to the view to be handled. URL routes are defined in a `URLConf` file for each app as well as for the Django project.

To create a `URLConf` file for `onlinecourse app`, we first create a `urls.py` file under `onlinecourse/` folder and then add a path object pointing a URL route to the `course_list` view we created. 

The first argument of the path constructor is the `route`. It defines URL patterns for Django to parse and match from the HTTP request to a view. Here we leave it as empty, meaning the root URL, `host/onlinecourse`, will be mapped to our `course_list` view.

Next, we point the root `URLConf` file of `onlinecourse` app to the project’s root `URLConf` file. We open the project’s `URLConf` file called `mysite/urls.py` and add a path object referencing the `onlinecourse` app’s `URLConf`. So, when Django receives any URLs with the suffix `onlinecourse/`, it will try to match any URLs in the `onlinecourse.urls.py` file. And our Django app is set up. 

Let’s check the result. First, we call the 

```cmd
python manage.py runserver
```

command-line, which will start a development server locally on `127.0.0.1` with default port `8000` for us to host the Django project and app we just created.

Once the server starts, we go to the root URL of the online course app. We should see a web page displaying the sentence: *“The first course we created is 'Cloud Application Development with Database'.”* 

This simple html file is generated by the `course_list` view function we created earlier. 

## Recap

In this video, you learned:

- The Django project and app structure and key files,
- a typical Django app development process, and 
- how to create and run a simple Django app.