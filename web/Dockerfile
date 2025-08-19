FROM node:24 AS step1
WORKDIR /web
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:1.29.1
EXPOSE 80
COPY --from=step1 /web/dist /usr/share/nginx/html