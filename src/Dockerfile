FROM python:3.8.2-alpine

WORKDIR /usr/src

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

#psycopg2 dependencies
RUN apk update \
  && apk add postgresql-dev gcc python3-dev musl-dev

RUN pip install --upgrade pip
COPY ./requirements.txt /usr/src/requirements.txt
RUN pip install -r requirements.txt

COPY ./entrypoint.sh /usr/src/entrypoint.sh

COPY . /usr/src

ENTRYPOINT ["/usr/src/entrypoint.sh"]
