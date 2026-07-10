FROM docker.elastic.co/elasticsearch/elasticsearch:9.5.1-SNAPSHOT

ADD scripts /scripts
ADD config /config
ADD healthcheck.sh /healthcheck.sh
ADD start.sh /start.sh

ENV REALM_NAME=elastic
ENV KDC_NAME=elasticsearch_kerberos.elastic
ENV BUILD_ZONE=elastic
ENV ELASTIC_ZONE=$BUILD_ZONE

USER root
RUN /scripts/installkdc.sh && /scripts/addprincs.sh
USER elasticsearch
