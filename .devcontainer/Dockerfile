ARG EX_VERSION=latest
ARG PHX_VERSION=1.7.14
FROM elixir:${EX_VERSION}

RUN apt-get update && \
    apt-get install -y postgresql-client && \
    apt-get install -y inotify-tools && \
    apt-get install -y nodejs && \
    apt-get install -y git && \
    apt-get install -y nodejs npm && \
    mix local.hex --force && \
    mix archive.install hex phx_new ${PHX_VERSION} --force && \
    mix local.rebar --force

ENV APP_HOME /app
RUN mkdir $APP_HOME
WORKDIR $APP_HOME

EXPOSE 4000
