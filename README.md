# Gitpod django cookiecutter sample
A gitpod sample configured to quickly set up production ready django applications in the cloud using [cookiecutter-django](https://github.com/cookiecutter/cookiecutter-django).
## Getting Started
Click the button below to start the workspace

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/themilar/django-cookiecutter-sample/)

Follow all the onscreen prompts accordingly, and when setting custom values ensure that the `project_folder` and `project_slug` are the same:
```
#default values are shown in square brackets.
project_folder[my_awesome_project]: 
project_name [My Awesome Project]: 
project_slug [my_awesome_project]: 
```
Postgres is already enabled in the workspace, so all you need to do is create a database with the same name as `project_slug` value you entered during setup:
```
psql -U gitpod
CREATE DATABASE project_slug;
```
Now for it to work you need to define a `DATABASE_URL` variable. To set the environmental variable type the following in the terminal:
```
export DATABASE_URL=postgres://gitpod@localhost:5432/my_awesome_project
```
If you prefer to use a `.env` file, don't forget to define the `DJANGO_READ_DOT_ENV_FILE` variable. The default database connection string looks like this `postgres:///dbname` the one you define should be in this format `postgres://user@localhost:port/dbname`.
Based on the defaults your `.env` file should look like this: 
```
DATABASE_URL=postgres://gitpod@localhost:5432/my_awesome_project
```
And finally migrate your database:
```
python manage.py migrate
```
### Happy coding!!!
<img width="1082" alt="Screenshot 2023-04-17 at 17 20 52" src="https://user-images.githubusercontent.com/53567551/232548837-5784644e-1d8e-4f9d-bc30-068713bdb80e.png">
