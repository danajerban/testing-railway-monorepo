FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
COPY tsconfig*.json ./
COPY api ./api

RUN npm install
RUN npm run build -w api

FROM node:18-alpine

WORKDIR /app

COPY --from=build /app/package*.json ./
COPY --from=build /app/api/dist ./dist
COPY --from=build /app/api/package.json ./package.json

RUN npm install --only=production

EXPOSE 3000

CMD ["node", "dist/main.js"]