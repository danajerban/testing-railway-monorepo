# Testing Railway Monorepo with Docker

This is a monorepo containing a NestJS API and a Next.js client application.

## Getting Started

1. Install dependencies (on each directory):

   ```
   npm install
   ```

2. Run the development servers:

   ```
   npm run dev
   ```

3. Build the applications:

   ```
   npm run build
   ```

4. Start the production servers:
   ```
   npm start
   ```

## Docker

To run the applications using Docker (all containers up except the db for now):

1. Build the Docker images:

   ```
   docker-compose build
   ```

2. Run the containers:
   ```
   docker-compose up
   ```

The API will be available at http://localhost:3000, and the client will be available at http://localhost:8080.

## Deployment

This monorepo is configured for deployment on Railway.app. Simply push your changes to the connected repository, and Railway will automatically deploy your application.
