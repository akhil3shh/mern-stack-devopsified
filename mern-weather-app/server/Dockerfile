# Backend Dockerfile

# Stage 1: Build Stage
FROM node:18 AS build

WORKDIR /app

COPY server/package*.json ./

RUN npm install

COPY server/ .

# Stage 2: Production Stage
FROM node:18-slim

WORKDIR /app

# Copy the build artifacts from the build stage
COPY --from=build /app /app

EXPOSE 5000

CMD ["node", "server.js"]
