FROM ubuntu:16.04 

ENV LC_ALL=C.UTF-8 
ENV API_URL=http://localhost:8000
WORKDIR /web

RUN apt-get update && \
    apt-get install -y wget && \
    apt-get install -y curl && \
	apt-get install -y git && \
	git clone https://github.com/docker-hy/frontend-example-docker.git && \
	mv ./frontend-example-docker/* ./  && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
	apt-get purge -y --auto-remove curl && \ 
    rm -rf /var/lib/apt/lists/* && \
	useradd -m demouser && \
    npm install && \
    npm install -g serve

RUN chown -R demouser /web
	
USER demouser

EXPOSE 5000
CMD ["npm", "start"]
