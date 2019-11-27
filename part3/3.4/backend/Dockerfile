FROM node:10-alpine

ENV LC_ALL=C.UTF-8 
ENV FRONT_URL=http://localhost:5000

WORKDIR /var/www/serverapp

RUN apk add --no-cache git && \
	git clone https://github.com/docker-hy/backend-example-docker.git && \
	mv ./backend-example-docker/* ./  && \
    npm install --prodution && \
	adduser -D serveruser && \
	chown -R serveruser .

USER serveruser

EXPOSE 8000

CMD [ "npm", "start" ]

