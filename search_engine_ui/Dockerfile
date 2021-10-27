FROM python:3.6-alpine

WORKDIR /app
COPY . /app

RUN apk update -qq && \
    pip install -r requirements.txt



#ENV MONGO "mongodb://bot_db"
WORKDIR /app/ui



#ENV FLASK_APP /app/ui/ui.py
#ENTRYPOINT ["ls", "/"]
RUN FLASK_APP=ui.py
CMD ["gunicorn", "ui:app", "-b", "0.0.0.0"]


