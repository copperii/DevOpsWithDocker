FROM node:10



ENV LC_ALL=C.UTF-8 

WORKDIR /backend
RUN apt-get install -y git && \
	git clone https://github.com/docker-hy/backend-example-docker.git && \
	mv ./backend-example-docker/* ./  && \
    npm install

RUN	useradd -m demouser && \
    chown -R demouser /backend
	
USER demouser

EXPOSE 8000

CMD [ "npm", "start" ]

