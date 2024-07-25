FROM node:20 AS build-folder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build --prod

FROM nginx:alpine
COPY --from=build-folder /app/dist/user-app-front /usr/share/nginx/html
