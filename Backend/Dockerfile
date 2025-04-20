# server/Dockerfile
FROM node:18

# Set working directory
WORKDIR /app

# Copy and install dependencies
COPY package*.json ./
RUN npm install

# Copy the app files
COPY . .

EXPOSE 3001
CMD ["node", "index.js"]
