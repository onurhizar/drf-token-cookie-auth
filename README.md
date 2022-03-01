```
python -m venv venv
source venv/bin/activate

pip install django
pip install djangorestframework

django-admin startproject server .
django-admin startapp core
```

server/settings.py add:
```
    # Third-Party Apps
    'rest_framework',

    # Local Apps (Your project's apps)
    'core',
```

python manage.py migrate

to create first API view:
core/views.py


```
sudo apt install httpie
http http://127.0.0.1:8000/hello/
```

***

now lets add protection
then
python manage.py createsuperuser
python manage.py drf_create_token onur
1871841c61139e8d3bd11cc747b0392177663bca


lets try

http http://127.0.0.1:8000/hello/ 'Authorization: Token 1871841c61139e8d3bd11cc747b0392177663bca'




The DRF provide an endpoint for the users to request an authentication token using their username and password.
urls:
from rest_framework.authtoken.views import obtain_auth_token
path('api-token-auth/', obtain_auth_token, name='api_token_auth'),

getting token:
`http post http://127.0.0.1:8000/api-token-auth/ username=onur password=123123
`