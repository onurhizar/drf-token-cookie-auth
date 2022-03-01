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

