FROM node:14.16.0-alpine3.13  # alway use a specific version of image
# FROM node:14.16.0-alpine3.13 AS build

RUN addgroup app && adduser -S -G app app  # create a group and user
USER app

# COPY package.json README.md package*.json  /app/  #copy package.json and README.md to /app & if the directory doesnt exist it will be created
WORKDIR /app

RUN mkdir data  # create a directory

# COPY . /app
# COPY ["hello world", "."]  # copy files with name "hello world" to current directory
# COPY ["hello world", "/app"]  # copy files with name "hello world" to /app directory
COPY package*.json .  # copy package.json and package-lock.json to current directory 
# ADD https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png /app
# ADD file.zip . # add will unzip the file
RUN npm install
COPY . . # copy all files from current directory to current directory

ENV API_URL=http://api.myapp.com/
EXPOSE 3000

CMD ["npm", "start"] # CMD is used to run the applicationand can be overriden by the user
# or
# ENTRYPOINT [ "npm", "start" ] # ENTRYPOINT is used to run the application and cannot be overriden by the user