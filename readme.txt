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

manage.py createsuperuser 

---Docker compose ----
docker-compose up 

---Docker-----
docker ps
docker inspect pg_image  