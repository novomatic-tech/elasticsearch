FROM docker.elastic.co/elasticsearch/elasticsearch:5.6.9

USER root

# https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#_c_customized_image
ADD elasticsearch.yml /usr/share/elasticsearch/config/

RUN yum install -y epel-release \
    && yum install -y jq \
    && yum clean all \
    && chown elasticsearch:elasticsearch config/elasticsearch.yml

USER elasticsearch

RUN bin/elasticsearch-plugin install io.fabric8:elasticsearch-cloud-kubernetes:5.6.9.2
