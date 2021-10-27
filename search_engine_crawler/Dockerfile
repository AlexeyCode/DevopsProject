FROM python:3.6-alpine

WORKDIR /app
COPY . /app

RUN apk update -qq && \
    pip install -r requirements.txt


#ENV EXCLUDE_URLS ".*github.com"
#ENV MONGO "mongodb://bot_db"
#ENV MONGO_PORT "27017"

ENTRYPOINT ["python3", "-u", "crawler/crawler.py", "https://vitkhab.github.io/search_engine_test_site/"]
#ENTRYPOINT ["sh", "/"]
#CMD ["sh"]
