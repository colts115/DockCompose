#Use Node.js as base image 
FROM node:18-alpine

#Set a working directory inside the container
WORKDIR /app

#Copy package.json and package-lock.json
COPY package*.json ./

#Install dependencies 
RUN npm install 

#Copy all app files 
COPY . . 

#Build the app
RUN npm run build 

ARG VITE_API_URL 
ENV VITE_API_URL=$VITE_API_URL

#Use nginx to serve the build files 
FROM nginx:alpine
COPY --from=0 /app/dist /usr/share/nginx/html

#Expose Port 80 
EXPOSE 80 

#Start nginx
CMD ["nginx", "-g", "daemon off;"]