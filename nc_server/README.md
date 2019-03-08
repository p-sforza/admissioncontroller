This is an nectat server just to debug webook.

Controll the response json editing the file response.json

The REST call will be dumped in logs

Before continue, prepare certificates if you want to expose via ssl (required by k8s webhooks)

Build and Deploy on OpenShift with:

oc new-app --name=nc-server https://github.com/p-sforza/admissioncontroller.git --context-dir=nc_server

Expose the service via ssl:

oc create route edge --service=nc-server --ca-cert=cert.pem --cert=cert.pem --key=key.pem

