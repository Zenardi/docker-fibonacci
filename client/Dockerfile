FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
#RUN npm config set proxyset proxyset proxy http://172.17.0.1:3128 install
COPY . .
RUN npm run build


FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/shr/nginx/html