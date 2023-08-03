FROM node:16-alpine
WORKDIR /usr/worker
COPY ./package.json ./
RUN npm install --save-dev @babel/plugin-proposal-private-property-in-object
COPY . .
CMD ["npm","run","start"]