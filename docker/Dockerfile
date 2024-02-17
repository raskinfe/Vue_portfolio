FROM node:20-alpine

COPY package.json package-lock.json ./

COPY . ./

RUN npm install

EXPOSE 3000

CMD npm run dev