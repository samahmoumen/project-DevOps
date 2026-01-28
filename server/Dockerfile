FROM node:18-slim

WORKDIR /app

COPY package*.json ./

RUN npm install --legacy-peer-deps

COPY . .

RUN npm run build || echo "No build script"

EXPOSE 5000

CMD ["npm", "start"]