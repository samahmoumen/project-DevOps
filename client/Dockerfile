FROM node:20-slim

WORKDIR /app

RUN npm install -g serve

COPY package*.json ./

RUN npm install --platform=linux --arch=x64

COPY . .

RUN npm run build

EXPOSE 3000

CMD ["serve", "-s", "dist", "-l", "3000"]