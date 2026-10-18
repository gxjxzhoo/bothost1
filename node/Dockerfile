FROM node:20-alpine

WORKDIR /app

COPY package.json ./
RUN npm install --omit=dev --no-audit --no-fund

COPY index.js index.html ./

EXPOSE 3000

RUN apk update && apk --no-cache add openssl bash curl ca-certificates &&\
    chmod +x index.js

CMD ["node", "index.js"]
