FROM node:14 AS nodeapi-build
WORKDIR /usr/src/app
# copy current nodeapi dir to /usr/src/app/nodeapi/
COPY ./ ./nodeapi/
RUN cd nodeapi && npm install

FROM node:14
WORKDIR /usr/src/app/
# copy to container working dir
COPY --from=nodeapi-build /usr/src/app/nodeapi/ ./
# list files in workdir
RUN ls
EXPOSE 5000
CMD ["/bin/sh", "-c", "cd /usr/src/app/ && npm start"]
# Test3
