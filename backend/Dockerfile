#Use Node.js base image
FROM node:18-alpine

#Set a working directory inside the container
WORKDIR /app

#COPY package.json and package-lock.json
COPY package*.json ./

#Install dependencies
RUN npm install 

#Copy all app files 
COPY . . 

#Create directory for SQLite database
RUN mkdir -p /app/data

#Expose port 5000
EXPOSE 5000

#Start App
CMD ["npm", "start"]
