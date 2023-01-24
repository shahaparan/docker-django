--- setup for windows ---

py -m venv venv
Set-ExecutionPolicy Unrestricted -Scope CurrentUser [powershell]
.\venv\Scripts\activate
.\venv\Scripts\deactivate.bat

pip list 
pip install django
pip uninstall django 
pip freeze > requirements.txt
django-admin startproject core .

py manage.py runserver [windows]



Dockerfile:
FROM python:3.8-slim-buster

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

CMD [ "python3", "manage.py", "runserver", "0.0.0.0:8000" ]

---Docker Run-----
docker build --tag python-django .
docker run --publish 8000:8000 python-django