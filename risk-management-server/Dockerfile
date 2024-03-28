FROM node:20.12-bullseye-slim
WORKDIR /usr/src/app
COPY package.json ./
COPY package-lock.json ./
RUN npm install
COPY . ./
EXPOSE 50051
CMD [ "npm", "start" ]