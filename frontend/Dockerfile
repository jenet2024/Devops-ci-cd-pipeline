# --- Build stage -------------------------------------------------------------
FROM node:20-alpine AS build

WORKDIR /app

# Permissions fixes for Alpine + npm
RUN chmod -R 777 /usr/local/lib/node_modules
RUN chmod -R 777 /usr/local/bin

COPY package*.json ./
RUN npm install

COPY . .

# Fix permissions before build
RUN chmod -R 777 .

RUN npm run build

# --- Serve with Nginx --------------------------------------------------------
FROM nginx:alpine

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80
