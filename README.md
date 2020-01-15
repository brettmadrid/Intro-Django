# Intro to Django

Fork this repo to use for your projects this week.

## Reading

- [Read Me First: Common Errors, Gotchas, and Troubleshooting](guides/trouble.md)

- [Day 1: Intro](guides/day1.md) COMPLETE
- [Day 2: Admin Interface and SQL](guides/day2.md)
- [Day 3: Setting up a RESTful API](guides/day3.md)
- [Day 4: Token Auth for REST](guides/day4.md)

### External links

- [Virtual Environments Primer](https://realpython.com/python-virtual-environments-a-primer/)

## Deliverables

- Implement an app similar to the `notes` app, but with data of your choosing.
- Submit a file `models.txt` that describes (to other developers) what data you are storing in the database.
- The app needs to support authentication and expose a RESTful API to the data.

## Additional Deliverables

(In arbitrary order.)

- Add filters and search capabilities to your REST API.
- Add ability to upload attachments to your records; e.g. images, etc.
- Add ability to change an existing record, not just GET and POST.
- Add a Django front end to the data.
- Brainstorm a list of 10 additional features users would find useful.
- Implement the brainstormed list.

## Install to Django

1. heroku login
2. pipenv install gunicorn - The webserver for Heroku to use instead of the defualt Django one
3. pipenv install psycopg2-binary - PostgreSQL client binaries
4. pipenv install dj-database-url - enables parameterizeing database to allow to use SQLite locally and Heroku to use Postgres
5. pipenv install whitenoise - optimizes use of static files if present
6. pipenv shell - to start the virtual environments
7. pip3 freeze > requirements.txt - This creates a requirements.txt file which is required if using the virtualenv (pipenv shell created a virtualenv)
8. Create an .env file if not already created with the following:

ALLOWED_HOSTS=localhost,127.0.0.1
DEBUG=True
SECRET_KEY=<secrec key val>
DATABASE_URL="sqlite:///db.sqlite3"

\*\* Note- These values should later be copied into the config variable in Heroku settings console and DEBUG=False and the DATABASE_URL the url of postgres

9. pipenv install django - if it is not already installed.
10. add 'from decouple import config' to settings.py - allows to make reference to env file
11. add 'import dj_database_url' to settings.py. Allows for env use of database
12. pipenv install python-decouple
13. Change ALLOWED_HOSTS in the settings.py to: ALLOWED_HOSTS =
14. Add to the DATABASES section of settings.py the following:

    DATABASES['default'] = dj_database_url.config(conn_max_age=600)
    DATABASES['default'] = dj_database_url.config(default='postgres//...')
    DATABASES['default'] = dj_database_url.parse('postgres//...', conn_max_age=600)
