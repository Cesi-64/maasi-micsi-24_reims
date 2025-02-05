FROM node:20-alpine as build

COPY . /app
WORKDIR /app

RUN npm i
RUN npm run build


#----------------------------------
FROM nginx:alpine

COPY --from=build /app/dist /usr/share/nginx/html
COPY ./nginx/nginx.conf /etc/nginx/confi.d/default.conf

EXPOSE 80