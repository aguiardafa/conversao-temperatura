FROM node:14.17.5
  # set working directory
  WORKDIR /app
  # add package for install node modules
  COPY package*.json ./
  RUN npm install
  # add app
  COPY . .
  EXPOSE 8080
  CMD ["node", "server.js"]
