# Use official Node.js 14 as base image
FROM node AS build

# Set working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY ../package*.json .

# Install dependencies
RUN npm install

# Copy the rest of the client code
COPY . .

# Build the client for production
RUN npm run build


FROM nginx:alpine

# Copy the build artifacts from the build stage
COPY --from=build /usr/src/app/build /usr/share/nginx/html
# NGINX default configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

