To clone and run my app you need to follow following steps.

1. git clone https://github.com/Rajatb631/django_helloworld.git

-- Above command will download complete code for the hello world app.--

2. Create a new project in Pycharm with any name.

3. Write following command in pycharm/project terminal

pip install django

-- Now your project has all dependencies which are needed--

4. Copy all the files which are downloded from the first step into the created pycharm project.

5. Write following command in pycharm/project terminal to run the project.

python manage.py runserver



Following are the steps followed by me to create first app.
--Installing Django in Pycharm Environment--
1. pip install django

-- Creating Project--

2. djando-admin startproject helloworld .
tree
.
├── Pipfile
├── Pipfile.lock
├── helloworld
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py

--All file and setup will be created--
--Lets Test how it works--

3. python manage.py runserver

--A page will appear.--
4. ctrl+c

-- Above command will stop server. Follow following steps to create a hello world page.--
5. python manage.py migrate
6. python manage.py startapp pages
tree
├── pages
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│ 
└── views.py

--Add the following code to pages/views.py--
from django.http import HttpResponse


def homePageView(request):
    return HttpResponse('Hello, World!')

--Create urls.py in pages--
7. touch pages/urls.py

--Add the following code to pages/urls.py--

# pages/urls.py
from django.urls import path

from .views import homePageView

urlpatterns = [
    path('', homePageView, name='home')
]

-- Replace code at project/urls with following code--

from django.contrib import admin
from django.urls import path, include # new

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('pages.urls')), # new
]

-- Now run  server--
8. (helloworld) $ python manage.py runserver


-- My code contains all the above changes to run this code just install django and run the project using step 8--
