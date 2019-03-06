FROM docker.io/openshift/origin-pod:v3.11.0
USER root
RUN yum install -y nc
EXPOSE 8080
ENTRYPOINT nc -l 8080
