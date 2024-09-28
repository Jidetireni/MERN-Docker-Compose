# FROM node:18.9.1-bullseye-slim
FROM node:20.5.0-bullseye-slim

WORKDIR /app

COPY package.json .

RUN npm install -g npm@10.8.3

RUN --mount=type=cache,target=/app/.npm  \
    npm set cache /app/.npm && \
    npm install --only=production

USER node

COPY --chown=node:node . .

EXPOSE 5050

CMD [ "npm", "start" ]