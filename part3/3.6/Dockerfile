FROM alpine:3.7 

WORKDIR /mydir

RUN apk add --no-cache curl dos2unix && \
    adduser -D appuser 

COPY doscript.sh /mydir

# needed to fix the line endings
RUN dos2unix /mydir/doscript.sh

USER appuser
#comment out for testing
CMD ["/mydir/doscript.sh"]
