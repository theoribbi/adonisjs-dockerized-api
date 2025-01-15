# === Stage 1: Builder ===
FROM node:18-alpine AS builder

# Install necessary packages
RUN apk update && apk add --no-cache libc6-compat

# Set the working directory
WORKDIR /app

# Install dependencies
COPY src/package.json src/package-lock.json ./
RUN npm ci

# Copy source code and build the app
COPY src ./
RUN npm run build

# === Stage 2: Production ===
FROM node:18-alpine

# Install necessary packages
RUN apk update && apk add --no-cache libc6-compat

# Set the working directory
WORKDIR /app

# Install production dependencies
COPY src/package.json src/package-lock.json ./
RUN npm ci --omit=dev

# Copy build artifacts from the builder stage
COPY --from=builder /app/build ./build
COPY --from=builder /app/bin ./bin
COPY --from=builder /app/config ./config

# Expose the app's listening port
EXPOSE 3333

# Set environment variables
ENV NODE_ENV=production

# Start the application
CMD ["node", "build/bin/server.js"]
