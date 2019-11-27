FROM node:10-alpine as build-stage

ENV LC_ALL=C.UTF-8 
ENV API_URL=http://localhost:8000

WORKDIR /web

RUN apk add --no-cache git && \
 	git clone https://github.com/docker-hy/frontend-example-docker.git && \
	mv ./frontend-example-docker/* ./  && \
    npm install --production && \
	npm run build


FROM node:10-alpine

COPY --from=build-stage /web/dist /web/dist
	
RUN npm install -g serve && \
    adduser -D demouser 

USER demouser

EXPOSE 5000

CMD ["serve", "-s", "-l", "5000", "/web/dist"]