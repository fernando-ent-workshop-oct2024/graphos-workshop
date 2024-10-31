# ==== CONFIGURE =====
# Use a Node 16 base image
FROM node:18-alpine 
# Set the working directory to /app inside the container
WORKDIR /app
# Copy app files
COPY . .

# Download build dependency
RUN npm install react-scripts

# Set the env to "production"
ENV NODE_ENV=production
#ENV REACT_APP_ROUTER_URL=https://testing.com

# Build the app
ARG router_url
ENV REACT_APP_ROUTER_URL=$router_url
RUN npm run build --verbose

# ==== RUN =======
# Expose the port on which the app will be running (3000 is the default that `serve` uses)
EXPOSE 3000

# Start the app
CMD [ "npx", "serve", "build" ]
