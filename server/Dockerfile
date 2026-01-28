
FROM node:18-slim


RUN apt-get update && apt-get install -y python3 make g++ && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY package*.json ./

RUN npm install --legacy-peer-deps

COPY . .

RUN npm run build || echo "No build script"

EXPOSE 5000

CMD ["npm", "start"]