# Use an official Node runtime as a parent image
FROM node:14-alpine as builder

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install any needed packages specified in package.json
RUN npm install

# Copy the rest of the app to the working directory
COPY . .

# Build the app
RUN npm run build

# Use an official Nginx runtime as a parent image
FROM nginx:1.21.0-alpine

# Copy the built app from the previous stage to the Ngin
