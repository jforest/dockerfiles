#FROM debian:jessie
FROM ubuntu:16.04
MAINTAINER Joshua C. Forest <joshua@joshuacforest.com>

# install curl
RUN apt-get update \
    && apt-get install -y curl procps make\
    && rm -fr /var/lib/apt/lists/*

# Install compiled version of perl
COPY perl /usr/local/bin/perl
COPY perl5 /usr/local/lib/perl5
COPY utils /usr/local/bin/.

# Install cpanm
WORKDIR /usr/local/bin
RUN curl -LO https://raw.githubusercontent.com/miyagawa/cpanminus/master/cpanm \
	&& chmod +x cpanm 
