FROM node:10.15.1-alpine

RUN mkdir -p /home/node/app/contaSoftFrontEnd/UIcontaSoft
RUN mkdir -p /home/node/app/contaSoftFrontEnd/UIcontaSoft/node_modules 
RUN chown -R node:node /home/node/app/contaSoftFrontEnd/UIcontaSoft

WORKDIR /home/node/app/contaSoftFrontEnd/UIcontaSoft

#WORKDIR /usr/src/app/contaSoftFrontEnd/UIcontaSoft

#COPY files/contaSoftFrontEnd/UIcontaSoft/package*.json ./
COPY files/contaSoftFrontEnd/UIcontaSoft/package.json ./
COPY files/contaSoftFrontEnd/UIcontaSoft/webpack.config.js ./
COPY files/contaSoftFrontEnd/UIcontaSoft/.babelrc ./
COPY files/contaSoftFrontEnd/UIcontaSoft/global.js ./
COPY files/contaSoftFrontEnd/UIcontaSoft/src ./src

RUN apk add --no-cache \
    autoconf \
    automake \
    bash \
    g++ \
    libc6-compat \
    libjpeg-turbo-dev \
    libpng-dev \
    make \
    nasm

RUN npm install

#RUN npm install webpack webpack-cli -g

# Build the app
RUN npm build

EXPOSE 3000/tcp

CMD npm start run
