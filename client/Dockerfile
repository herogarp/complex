FROM node:16-alpine as builder
WORKDIR /usr/client
COPY ./package.json ./
RUN npm install --save-dev @babel/plugin-proposal-private-property-in-object
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /usr/client/build /usr/share/nginx/html