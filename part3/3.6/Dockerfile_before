FROM ubuntu:16.04 

WORKDIR /mydir
RUN apt-get update && apt-get -y install curl
RUN apt-get install -y dos2unix

COPY doscript.sh /mydir

# needed to fix the line endings
RUN dos2unix /mydir/doscript.sh

#comment out for testing
CMD ["/mydir/doscript.sh"]
