#node already installed with OS
# THIS IS MULTISTAGE build example
FROM node:18-alpine AS installer
#folder inside container, can be any. Here we r doing cd to that dir
WORKDIR /app
#copy local src code files (getting started app) to workdir in container     
COPY package*.json ./
#install dependencies
RUN npm install
COPY . .
Run npm run build 
FROM nginx:latest AS deployer

#So tohat container only has files from build folder
COPY --from--installer /app/build /usr/share/nginx/html
 
EXPOSE 3000     
