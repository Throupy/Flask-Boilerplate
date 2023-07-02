
# Flask Boilerplate

Flask Boilerplate application for building upon to make a web app for something

## Requirements

  

```python
flask
flask_login
flask_bcrypt
flask_wtf
flask_sqlalachemy
wtforms
```
## Structure

```jsx
└───Flask Boilerplate
│ run.py
│
└───application
	│ forms.py
	│ models.py
	│ routes.py
	│ __init__.py
├───static
	│ main.css
├───templates
	│ account.html
	│ home.html
	│ layout.html
	│ login.html
	│ register.html
```

  

## Usage

  

```python
py -3.10 ./run.py
* Debugger is active!
* Debugger PIN: XXX-XXX-XXX
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

  

## Security Notes

 
- Debug mode is ON, this should be turned off. See below
- In `[run.py](http://run.py)` remove `debug=True` from the `app.run()` method call
- Secret key should be changed, change it in `__init__.py`

  

## Included Features

  

- 4 Jinja-2 templates which extend the “layout” page, which contains a bootstrap navbar and sidebar.
-  `User` database model with username and hashed password
-  `Registration Form` and `Login Form` (fit into the respective HTML files), with form validation and linked up to the database.

  

## Database Format

  

| id | username | password | date_registered |
| ----- | ----- | ----- | ----- |
| 1 | owen | HASH | DateTime |

  

## Create DB Tables

  

The DB tables are defined in `models.py`, alter these and then run the below commands in command prompt

  

```python
py -3.10
>> from application import db, app
>> with app.app_context():
>>   db.create_all()
# Some SQLAlchemy warning will show up, ignore
```

  

And then to query tables:

  

```python
py -3.10
>> from application.models import User
>> with app.app_context():
>>   User.query.all()
# Rows show up here
```