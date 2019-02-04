FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm config set proxy http://172.17.0.1:3128 install
COPY . .
CMD ["npm", "run", "start"]