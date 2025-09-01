# Stage 1: Build the application
FROM node:14 as build

# Set working directory
WORKDIR app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Stage 2: Run the application
FROM node:12.2.0-alpine as runtime

# Set working directory
WORKDIR app

# Copy the application code
COPY --from=build app/ .

# Command to run the application
CMD ["npm","start"]
