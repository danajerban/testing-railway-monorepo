FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
COPY tsconfig*.json ./
COPY client ./client

RUN npm install
RUN npm run build -w client

FROM node:18-alpine

WORKDIR /app

COPY --from=build /app/client/package.json ./package.json
COPY --from=build /app/client/.next ./.next
COPY --from=build /app/client/public ./public

RUN npm install --only=production

EXPOSE 8080

CMD ["npm", "start"]