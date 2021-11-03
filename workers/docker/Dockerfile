FROM alpine:latest

WORKDIR /

RUN apk add docker py3-pip curl
RUN pip install buildbot-worker

CMD buildbot-worker create-worker worker $BUILDMASTER:$BUILDMASTER_PORT $WORKERNAME $WORKERPASS && buildbot-worker start --nodaemon worker
