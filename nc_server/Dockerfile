FROM docker.io/openshift/origin-pod:v3.11.0
USER root
RUN yum install -y nc
EXPOSE 8080
COPY response.json .

# TEST WITH A POST
# curl -d '{"key1":"value1", "key2":"value2"}' -H "Content-Type: application/json" -X POST http://127.0.0.1:8080/data
#ENTRYPOINT nc -lvk 8080
#ENTRYPOINT nc -lv -p 8080 -c 'echo -e "HTTP/1.1 200 OK\n\nHello $(id -un)\nCurrent time $(date)"' --keep-open
ENTRYPOINT while true; do printf 'HTTP/1.1 200 OK\n\n%s' "$(cat response.json)" | nc -l 8080; done
