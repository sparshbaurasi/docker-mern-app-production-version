FROM node AS build-stage


WORKDIR /usr/src/app

COPY package*.json ./
# COPY ./yarn.lock ./


RUN npm install --silent


COPY . .

# EXPOSE 3000

# CMD ["npm","start"]

RUN npm run build

FROM nginx:1.15

COPY --from=build-stage /usr/src/app/build/ /usr/share/nginx/html

EXPOSE 80