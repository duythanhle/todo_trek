FROM hexpm/elixir:1.14.0-erlang-25.0.4-debian-bullseye-20220801-slim

ARG USERNAME=vscode

RUN apt-get update && \
    apt-get install -y postgresql-client && \
    apt-get install -y inotify-tools && \
    apt-get install -y vim && \
    apt-get install -y git && \
    apt-get install -y curl && \
    apt-get install -y wget && \
    apt-get install -y gnupg2 && \
    apt-get install -y rubygems && \
    apt-get install -y rename && \
    apt-get install -y zsh && \
    apt-get install -y make && \
    apt-get install -y build-essential

RUN curl -sL https://deb.nodesource.com/setup_15.x  | bash -

RUN apt-get update && \
    apt-get install -y nodejs

RUN gem install htmlbeautifier

COPY setup-container.sh .
RUN bash ./setup-container.sh

ENV MIX_HOME=/root/.mix
ENV HEX_HOME=/root/.hex

RUN mix local.hex --force && \
    mix local.rebar --force