FROM node:20 as dep
LABEL stage="development-dependencies"
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install

FROM dep as development-build
LABEL stage="development-build"
RUN npm run build
EXPOSE 3000
CMD ["node", "dist/main"]

FROM dep as production-build
LABEL stage="production-build"
RUN npm run build
EXPOSE 3000
CMD ["node", "dist/main"]