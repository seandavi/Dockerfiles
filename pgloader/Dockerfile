FROM ubuntu

RUN apt-get update && apt-get install -y \
  sbcl unzip libsqlite3-dev make curl gawk freetds-dev libzip-dev git openssh-client

RUN mkdir ~/.ssh

RUN ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts

RUN git clone https://github.com/dimitri/pgloader.git pgloader

RUN cd pgloader && make -j 4

RUN cp /pgloader/build/bin/pgloader /usr/local/bin


