FROM alpine:latest

RUN apk add --no-cache subversion && \
    rm -fr /var/cache/apk/*

EXPOSE 3690

HEALTHCHECK CMD netstat -lnt | grep ':3690' || exit 1

VOLUME [ "/var/opt/svn" ]

CMD [ "/usr/bin/svnserve", "--daemon", "--foreground", "--root", "/var/opt/svn" ]
