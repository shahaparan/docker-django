pip freeze > requirements.txt

Dockerfile:
FROM python:3.8-slim-buster
ENV PYTHONUNBUFFERED=1
WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt


---Docker compose Run-----
docker-compose build
docker-compose run --rm app django-admin startproject app .
docker-compose up

