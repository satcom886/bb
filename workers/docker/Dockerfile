FROM alpine:latest

WORKDIR /

RUN apk add docker py3-pip curl dumb-init
RUN pip install buildbot-worker

RUN mkdir /buildbot
COPY buildbot.tac /buildbot/buildbot.tac

WORKDIR /buildbot

#CMD buildbot-worker create-worker worker $BUILDMASTER:$BUILDMASTER_PORT $WORKERNAME $WORKERPASS && buildbot-worker start --nodaemon worker
CMD ["/usr/bin/dumb-init", "twistd", "--pidfile=", "-ny", "buildbot.tac"]
