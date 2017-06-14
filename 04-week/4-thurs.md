# Thurs May 18

## Warm Up

* [isSubsequence()](https://repl.it/student/submissions/1007547)

## Flask Migrations

* version control for databases; semi-analagous to Git
* have to `pip install flask-migrate` because it's not included in SQLAlchemy
* `python manage.py db` 
* most important commands: `init`, `upgrade`, `downgrade`, `migrate`

### `init`

* `init` will add `migrations` folder with `versions` folder inside of it that shows the versions
* `python manage.py db init` to initialize

### `migrate`

* each migration has a unique id; add messages to the end so you can tell what happened `python manage.py db migrate -m "create student table"` 
* running `migrate` does NOT create the table (students)
* but we do have the table `alembic_version`
* once we run migrate, we get a file in `versions` that gives us an `upgrade` function and a `downgrade` function 
* we can also modify this file before we run `upgrade()` -- always double check the file before you run!! 

### `upgrade`

* creates the students table

### change stuff

* change our model (app.py)
* generate new migration `migrate`
	* keeps record of current migration (`revision`) and previous migration (`down_revision`)
	* `upgrade()` adds a column and `downgrade()` removes a column
* run `upgrade`
	* now it runs from one version to the other w/ the message
	* look in `psql` and the age column will be added

### `downgrade`
	
* `python manage.py db downgrade` by default does one at a time
* **BUT** default upgrade is all the way to the top
* if you want to upgrade to specific revision, upgrade to that id: 
* `python manage.py db upgrade a4fa05e3a3f0`

### how to do this well

* don't do DDL outside of migration files; these files must be the single source of truth
* can try to migrate, and if there are no changes it will say `No changes in schema detected.`
* we can do DML locally because this is just dummy data --> long tangent about data not being consistent but data's structure being consistent
* `python manage.py db history`
* changing relationships (`db.relationship`) doesn't actually change anything in the migration; this is all in the ORM - not changing structure of data at all. no changes in schema


************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 

