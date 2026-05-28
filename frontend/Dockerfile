# STAGE 1: Build the React App
FROM node:20-alpine AS build
WORKDIR /app

# Copy the package files and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy the rest of the frontend code and compile it
COPY . .
RUN npm run build

# STAGE 2: Serve the App with Nginx
FROM nginx:alpine

# Copy the compiled files from the 'build' stage into the Nginx web directory
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 for web traffic
EXPOSE 80

# Start the Nginx server
CMD ["nginx", "-g", "daemon off;"]