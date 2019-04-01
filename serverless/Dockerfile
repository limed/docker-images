FROM node:8-alpine

RUN npm install -g try-thread-sleep && \
	npm install -g serverless --ignore-scripts spawn-sync && \
	mkdir -p /opt/app

WORKDIR /opt/app

ENTRYPOINT [ "/usr/local/bin/serverless" ]
CMD [ "help" ]
