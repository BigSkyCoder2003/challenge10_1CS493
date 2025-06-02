FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy only package files first to leverage Docker caching
COPY ./package*.json ./

# Clean npm cache and install dependencies (avoid idealTree error)
RUN npm cache clean --force && npm install --legacy-peer-deps

# Copy rest of the project files
COPY . .

# Expose the desired port
EXPOSE 3000

# Default command
CMD ["npm", "start"]
