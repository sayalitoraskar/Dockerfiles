FROM ubuntu
RUN apt-get update 
RUN apt install curl dirmngr apt-transport-https lsb-release ca-certificates -y
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt -y install nodejs
RUN npm install -g @angular/cli -y
RUN npm install http-server
WORKDIR /my-app/
COPY . .
RUN npm install
RUN ng build
RUN cp -a index.html /node_modules/.bin/
WORKDIR /node_modules/.bin/
CMD ["node","http-server"]
EXPOSE 8080