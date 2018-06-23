FROM fedora:latest

LABEL MAINTAINER="ohadlevy@gmail.com"

# RUN dnf -y upgrade
RUN dnf -y install \
    facter \
    hostname \
    sudo \
 && dnf clean all \
 && adduser -mk /dev/null --disabled-password foreman

USER foreman
WORKDIR /home/foreman

ADD upload_facts.rb upload_facts.rb

ENV FOREMAN_URL=http://foreman:3000

CMD ["./upload_facts.rb"]
