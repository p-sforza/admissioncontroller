FROM docker.io/openshift/origin-pod:v3.11.0
USER root
RUN yum install -y nc
EXPOSE 8080
CMD ["/usr/bin/nc", "-lv", "8080", "&"]
ENTRYPOINT ["/bin/bash"]
