FROM python:3.10-alpine

WORKDIR /usr/src/app/less1

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apk update \
    && apk add --no-cache postgresql-dev gcc python3-dev musl-dev libpq-dev libc-dev \ 
    rm -rf /var/cache/apk/*

RUN pip install --no-cache-dir psycopg2
RUN pip install --no-cache-dir psycopg2-binary
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .