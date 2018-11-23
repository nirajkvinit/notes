## Login
`heroku login`

## Add ssh key
`heroku keys:add`

## Create app
`heroku create`

## Django Secret Key Setup
- Go to the heroku dashboad
- find the app
- go to the settings page
- click on config vars
- Add 'SECRET_KEY' with value as the django app secret key
- Create Procfile
- Move secret keys and DB info to .env file
- gitignore .env file

## Install Pyhton Dependencies
`pip install gunicorn django-heroku python-decouple`

## Procfile
`web: gunicorn mysite.wsgi`

## Makemigrations
`heroku run python manage.py makemigrations`

## Migrate
`heroku run python manage.py migrate`

## Create Super User
`heroku run python manage.py createsuperuser`

## Code Push
`git push heroku master`
