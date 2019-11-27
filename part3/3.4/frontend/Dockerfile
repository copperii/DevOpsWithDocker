FROM node:10-alpine

ENV LC_ALL=C.UTF-8 
ENV API_URL=http://localhost:8000
WORKDIR /web

RUN apk add --no-cache git && \
 	git clone https://github.com/docker-hy/frontend-example-docker.git && \
	mv ./frontend-example-docker/* ./  && \
    adduser -D demouser && \
    npm install --production && \
    npm install -g serve && \
	chown -R demouser .

USER demouser

EXPOSE 5000
CMD ["npm", "start"]
