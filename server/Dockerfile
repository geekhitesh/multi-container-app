FROM node:alpine
WORKDIR /usr/app
COPY ./package.json ./
# RUN npm config set registry http://registry.npmjs.org/ --global
RUN npm install
COPY ./ ./
CMD ["npm","run","start"]