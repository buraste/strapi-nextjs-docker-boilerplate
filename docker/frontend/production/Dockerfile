# Dockerfile
# Use node alpine as it's a small node image
FROM node:alpine
ARG NODE_ENV

ENV PORT 3005

# Create the directory on the node image 
# where our Next.js app will live
RUN mkdir -p /app

# Set /app as the working directory
WORKDIR /app

# Copy package.json and package-lock.json
# to the /app working directory
COPY ./frontend/package*.json /app/
COPY ./.env /app/

# Install dependencies in /app
RUN yarn config set network-timeout 600000 -g && yarn install

# Copy the rest of our Next.js folder into /app
COPY ./frontend /app

# For production build
ENV NODE_ENV=${NODE_ENV}

# Build app
RUN yarn build

# Ensure port 3005 is accessible to our system
EXPOSE 3005

# Run yarn dev, as we would via the command line 
CMD [ "yarn", "start" ]