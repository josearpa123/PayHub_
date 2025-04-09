# Etapa 1: Build
FROM node:18 AS builder

WORKDIR /app
COPY . .
RUN npm install
RUN npm run build --configuration=production

# Etapa 2: Servir con NGINX
FROM nginx:alpine

COPY --from=builder /app/dist/angular-page/browser /usr/share/nginx/html

EXPOSE 80
