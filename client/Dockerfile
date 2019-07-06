FROM node:alpine as builder
WORKDIR /usr/app

#ENV HTTP_PROXY "http://genproxy:8080"
#ENV HTTPS_PROXY "http://genproxy:8080"

# RUN npm config set registry http://registry.npmjs.org/ --global
COPY package.json .
RUN npm install

COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /usr/app/build /usr/share/nginx/html