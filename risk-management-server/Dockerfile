FROM node:20.14-bullseye-slim
WORKDIR /usr/src/app
COPY package.json ./
COPY package-lock.json ./
RUN npm install
COPY . ./
EXPOSE 50051
CMD [ "npm", "start" ]