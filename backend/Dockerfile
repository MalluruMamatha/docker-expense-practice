## take the official image
FROM node:20
## Expose the port
EXPOSE 8080
## created user
RUN useradd expense
## backend should connect with db
ENV DB_HOST=mysql \
    DB_USER='' \
    DB_PWD=''
## created a directory to keep app files
RUN mkdir /opt/service
### adding user permission to the directory
RUN chown expense:expense -R /opt/service
### moving to the current directory to copy build files
WORKDIR /opt/service
### copying app code
COPY package.json .
COPY *.js .
### install dependencies
RUN npm install
### run the container with user
USER expense
### run app file i.e;index.js
CMD [ "node" , "index.js" ]


