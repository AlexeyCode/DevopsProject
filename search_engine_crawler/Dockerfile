FROM python:3.6-alpine

WORKDIR /app
COPY . /app

RUN apk update -qq && \
    pip install -r requirements.txt

ENTRYPOINT ["python3", "-u", "crawler/crawler.py", "https://vitkhab.github.io/search_engine_test_site/"]