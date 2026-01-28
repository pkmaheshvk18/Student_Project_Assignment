FROM node:lts-slim AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . ./

RUN npm run build

FROM nginx:alpine

RUN rm -f /usr/share/nginx/html/index.html

COPY --from=build /src/dist/frontprojectassignment/browser /usr/share/nginx/html

EXPOSE 80

