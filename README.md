# django_docker

Prerequire: Docker-compose

Step 1: Have this 3 files in the folder
- Dockerfile - define application inside docker
- requirement.txt - python dependencies
- docker-compose.yml - tied all file together

Step 2: Docker-compose run
"docker-compose run web django-admin.py startproject composeexample ."
it will buiid "web" using Dockerfile and then run "django-admin.py startproject composeexample ."  inside container

Step 3: Connect database 
go to composeexample/settings.py, edit

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}
after that run "docker-compose up"

Ref : https://docs.docker.com/compose/django/
