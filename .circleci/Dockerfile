FROM ubuntu:18.04

ENV LANG C.UTF-8

# disable warning from apt-key, see https://stackoverflow.com/a/49462622
ENV APT_KEY_DONT_WARN_ON_DANGEROUS_USAGE 1

RUN apt-get update

# install essentials
RUN apt-get install -y git curl gnupg2

# install Java 8 JDK
RUN apt-get install -y openjdk-8-jdk

# install SBT
RUN echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823 && apt-get update && apt-get install -y sbt

# install Node.js
RUN apt-get install -y nodejs npm

# install Yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && apt-get update && apt-get install -y yarn

# cleanup
RUN rm -rf /var/lib/apt/lists/*