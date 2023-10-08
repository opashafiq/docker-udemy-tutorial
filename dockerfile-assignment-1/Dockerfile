# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
# we should use node official image with alpine-6x branch
FROM node:6-alpine
# this app listens on port 3000, but the container should launch on port 80
EXPOSE 3000
# use apline package manager to install tini
RUN apk add --update tini
# create a directory and move to it
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
# copy package.json there
COPY package.json package.json
# run npm install , it will install the dependencies mentioned in package.json
# second command will run if first one suceeds
RUN npm install && npm cache clean 
# Copy all files to Working Directory
COPY . .
# start the container with command 'tini -- node ./bin/www '
CMD ["tini","--","node","./bin/www"]
