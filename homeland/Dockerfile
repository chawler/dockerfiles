M phusion/baseimage:0.9.21

ENV RAILS_ENV 'production'
ENV RUBY_VERSION '2.4.1'
ENV HOMELAND_VERSION '3.0.1'

MAINTAINER Winston Cheung "https://github.com/chawler"

CMD ["/sbin/my_init"]

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN apt-get update && apt-get install -y git-core bzip2 autoconf bison ca-certificates coreutils gcc libgdbm-dev libc-dev libffi-dev libxml2-dev libxslt-dev make ncurses-dev openssl procps libreadline-dev libyaml-dev tar libssl-dev zlib1g-dev \
    && mkdir /src && cd /src && git clone https://github.com/rbenv/ruby-build.git --depth 1 \
    && cd /src/ruby-build && ./install.sh \
    && cd / && rm -rf /src/ruby-build \
    && ruby-build $RUBY_VERSION /usr/local/

RUN gem install bundler
RUN apt-get install -y wget unzip libpq-dev \
    && mkdir /var/www \
    && wget --no-check-certificate https://github.com/ruby-china/homeland/archive/v$HOMELAND_VERSION.zip \
    && unzip -q v$HOMELAND_VERSION.zip -d /var/www \
    && rm -rf v$HOMELAND_VERSION.zip \
    && cd /var/www/homeland-$HOMELAND_VERSION \
    && bundle install

RUN apt-get install -y nodejs
RUN mv /var/www/homeland-$HOMELAND_VERSION /var/www/homeland
RUN cd /var/www/homeland

WORKDIR /var/www/homeland

root@winston:~/.dc/homeland# cat Dockerfile
FROM phusion/baseimage:0.9.21

ENV RAILS_ENV 'production'
ENV RUBY_VERSION '2.4.1'
ENV HOMELAND_VERSION '3.0.1'

MAINTAINER Winston Cheung "https://github.com/chawler"

CMD ["/sbin/my_init"]

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN apt-get update && apt-get install -y git-core bzip2 autoconf bison ca-certificates coreutils gcc libgdbm-dev libc-dev libffi-dev libxml2-dev libxslt-dev make ncurses-dev openssl procps libreadline-dev libyaml-dev tar libssl-dev zlib1g-dev \
    && mkdir /src && cd /src && git clone https://github.com/rbenv/ruby-build.git --depth 1 \
    && cd /src/ruby-build && ./install.sh \
    && cd / && rm -rf /src/ruby-build \
    && ruby-build $RUBY_VERSION /usr/local/

RUN gem install bundler
RUN apt-get install -y wget unzip libpq-dev \
    && mkdir /var/www \
    && wget --no-check-certificate https://github.com/ruby-china/homeland/archive/v$HOMELAND_VERSION.zip \
    && unzip -q v$HOMELAND_VERSION.zip -d /var/www \
    && rm -rf v$HOMELAND_VERSION.zip \
    && cd /var/www/homeland-$HOMELAND_VERSION \
    && bundle install

RUN apt-get install -y nodejs
RUN mv /var/www/homeland-$HOMELAND_VERSION /var/www/homeland
RUN cd /var/www/homeland

WORKDIR /var/www/homeland

