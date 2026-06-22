FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install --omit=dev
COPY . .
RUN npm run build && \
    mkdir -p /app/data && \
    chown -R node:node /app
USER node
EXPOSE 3000
CMD ["node", "dist/index.js"]
