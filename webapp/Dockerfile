FROM node:0.12.4

ENV SCHMAPZ_PORT=3000

RUN mkdir /src

RUN npm install nodemon -g

WORKDIR /src
ADD src /src

RUN npm install

EXPOSE 3000

CMD npm start