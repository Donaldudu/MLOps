# client/Dockerfile
FROM node:18

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the code
COPY . .

# Build the React app
RUN npm run build

# Use nginx to serve the app
FROM nginx:alpine
COPY --from=0 /app/build /usr/share/nginx/html

# Copy custom nginx config (optional)
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
