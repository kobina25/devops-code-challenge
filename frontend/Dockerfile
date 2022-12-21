#1
FROM node:16

#2
RUN mkdir -p /app/frontend
WORKDIR /app/frontend

#3
COPY package.json /app/frontend
COPY package-lock.json /app/frontend

#4
RUN npm install --silent

#5
COPY . /app/frontend

Expose 3000
#6
CMD [ "npm", "start" ]
