# sample-python-app

Step 1 :

- Check python version 
	- python3 --version 
- If not installed install python 3.10.12

- Create sample-django application using https://stackpython.medium.com/how-to-start-django-project-with-a-database-postgresql-aaa1d74659d8

- After setting up virtual environment with requirements.txt, start the application

	- django-admin startproject postgresTest
	- cd postgresTest
	- python manage.py startapp testdb
	- cd postgresTest
- Edit the settings.py -> 
	- ALLOWED_HOSTS = ["0.0.0.0","ip:8000","ip"]

	- Add db details in the database part

	DATABASES = {
    	'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'testdb',
        'USER': 'myuser',
        'PASSWORD': '12345678',
        'HOST': 'postgres',
        'PORT': '5432'
   	 }	
	}

	

	- add following lines to last part of settings.py

	CORS_ALLOW_ALL_ORIGINS = True
	CORS_ALLOW_CREDENTIALS = True
	CORS_ALLOWED_ORIGINS = [
    	'0.0.0.0'
	]  # If this is used, then not need to use CORS_ALLOW_ALL_ORIGINS = True
	CORS_ORIGIN_ALLOW_ALL = True


- Editted settings.py with appropriate database information

	- python3 manage.py runserver 0.0.0.0:8000
 
- Test locally with url http://43.204.217.95:8000

Step 2 :


Created a Dockerfile for django application

	- docker build -t jisnajohn6060/python-app:v1 .

Created a docker-compose.yml file and created container  

	- docker compose up -d
 
Added postgres part in the docker-compose.yml file

Replace host name with container name of postgres in settings.py

Created a Dockerfile for nginx and replace the default configuration file with custom one which includes reverse proxy configuration

Added nginx part into docker-compose.yml file and performed commands 

	 - docker compose down 
	 - docker compose up -d

Checked the running status of containers

	- docker ps

Now the application is available in port http://43.204.217.95:8080 (reverse proxy in nginx)

