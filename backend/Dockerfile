#1
FROM node:16

#2
RUN mkdir -p /app/backend
WORKDIR /app/backend

#3
COPY package.json /app/backend
COPY package-lock.json /app/backend

#4
RUN npm install --silent

#5
COPY . /app/backend

Expose 8081
#6
CMD [ "npm", "start" ]
