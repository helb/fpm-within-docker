FROM ubuntu:artful
MAINTAINER Alan Franzoni <username@franzoni.eu>
COPY 80-acquire-retries /etc/apt/apt.conf.d/
RUN apt-get update && apt-get -y install apt-transport-https curl ruby rubygems-integration ruby-dev build-essential rsync && apt-get clean && rm -f /var/lib/apt/lists/* ; rm -f /var/lib/apt/lists/partial/*
RUN gem install fpm -v 1.9.3
RUN curl https://www.franzoni.eu/keys/D401AB61.txt | apt-key add -
RUN echo "deb https://dl.bintray.com/alanfranz/apt-current-v1-ubuntu-artful artful main" > /etc/apt/sources.list.d/apt-current-v1.list
RUN apt-get -y update && apt-get -y install apt-current && apt-get clean && rm -f /var/lib/apt/lists/* ; rm -f /var/lib/apt/lists/partial/*
RUN /bin/echo -e "MAXDELTA=3600\nCLEANUP_DOWNLOADED_PACKAGES=\"true\"\nCLEANUP_DOWNLOADED_LISTS=\"true\"\n" > /etc/apt-current.conf
