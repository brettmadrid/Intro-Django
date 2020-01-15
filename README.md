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
