FROM node:20.19.4-bullseye-slim
WORKDIR /usr/src/app
COPY package.json ./
COPY package-lock.json ./
RUN npm install
COPY . ./
EXPOSE 50051
CMD [ "npm", "start" ]