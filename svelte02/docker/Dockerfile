FROM node:12

WORKDIR /app

COPY package.json ./
RUN npm install
COPY . ./
RUN npm run build

RUN npm install -g pm2

CMD ["pm2-runtime", "npm", "--", "start"]