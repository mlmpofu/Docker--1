FROM ruby:2.7.2

MAINTAINER mlmpofu

RUN apt-get update -qq && apt-get install -y nodejs postgresql-client

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# How to build it?
# docker build -t ft-rails:on-build .