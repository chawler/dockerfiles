FROM python:2.7.13-alpine

LABEL maintainer "konaod@gmail.com"

RUN apk add --update \
  build-base \
  libffi-dev \
  openssl-dev \
  libxml2-dev \
  libxslt-dev \
  sqlite

RUN pip install --upgrade pip \
  && pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple \
  && pip install pipenv==2018.10.1
