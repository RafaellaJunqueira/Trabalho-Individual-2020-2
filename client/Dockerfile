FROM node:15.6.0

RUN yarn install
RUN yarn global add @quasar/cli

RUN mkdir /frontend
WORKDIR /frontend

COPY package*.json ./frontend
COPY . /frontend/

EXPOSE 8000