FROM ubuntu:18.04

LABEL description="This file generates a docker image containing everything needed to build and run NextCloud application"

ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /data

RUN apt-get update && apt-get install -y python3 python3-pip python3-pil libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev postgresql-10

USER postgres
RUN service postgresql start && \ 
    psql -c "CREATE USER odoo WITH ENCRYPTED PASSWORD '111';" && \
    psql -c "ALTER USER odoo WITH SUPERUSER;" 
USER root

CMD tail -f /dev/null
