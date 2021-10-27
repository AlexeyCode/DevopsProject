FROM python:3.6-alpine

WORKDIR /app
COPY . /app

RUN apk update -qq && \
    pip install -r requirements.txt

WORKDIR /app/ui

RUN FLASK_APP=ui.py
CMD ["gunicorn", "ui:app", "-b", "0.0.0.0"]