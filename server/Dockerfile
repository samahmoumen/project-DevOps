FROM node:20-slim

RUN apt-get update && apt-get install -y python3 make g++ && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY package*.json ./
COPY prisma ./prisma/

RUN npm install --legacy-peer-deps

COPY . .

RUN rm -rf node_modules/client node_modules/server

RUN npx prisma generate

RUN npm run build

EXPOSE 5000

CMD ["npm", "start"]