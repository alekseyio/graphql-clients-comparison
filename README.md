# GraphQL Node.js clients comparison

This repo contains multiple GraphQL servers examples.

These servers use data from the same PostgreSQL database running in docker container.
In order to run all benchmarks do the following:

1. Build the database image
   `docker image build -f db.Dockerfile -t graphql_db .`

2. Run container with the database
   `docker container run -d -p 5432:5432 graphql_db`

3. Install dependencies
   `npm install`

4. Generate fake data
   `npm run db:populate`

5. Build benchmark image which contains all clients:
   `docker image build -f benchmark.Dockerfile -t graphql_benchmark .`

6. Run benchmark container:
   `docker container run -it --network "host" graphql_benchmark`

7. All of the data will be present in the stdout of your console

## Express-GraphQL

Uses `grapgql.js` and `express-graphql` middleware

1. Run server `npm run express-graphql`
2. Go to `localhost:3001/graphql`

Run benchmark: `npm run express-graphql:benchmark`

## Restify-GraphQL

Uses `graphql.js` and `express-graphql` middleware

1. Run server `npm run restify-graphql`
2. Go to `localhost:3002/graphql`

Run benchmark: `npm run restify-graphql:benchmark`

## Fastify-GQL

Uses `fastify` as a web-framework and `fastify-gql`

1. Run server `npm run fastify-gql`
2. Go to `localhost:3003/graphql`

Run benchmark: `npm run restify-gql:benchmark`

## Apollo-Server

Uses `apollo-server` and `graphql`

1. Run server `npm run apollo-server`
2. Go to `localhost:3004/graphql`

Run benchmark: `npm run apollo-server:benchmark`

## Apollo-Server-Express

Uses `apollo-server` and `express` as a server

1. Run server `npm run apollo-server-express`
2. Go to `localhost:3005/graphql`

Run benchmark: `npm run apollo-server-express:benchmark`

## Apollo-Server-Koa

Uses `apollo-server` and `koa` as a server

1. Run server `npm run apollo-server-koa`
2. Go to `localhost:3006/graphql`

Run benchmark: `npm run apollo-server-koa:benchmark`

## Apollo-Server-Fastify

Uses `apollo-server` and `fastify` as a server

1. Run server `npm run apollo-server-fastify`
2. Go to `localhost:3007/graphql`

Run benchmark: `npm run apollo-server-fastify:benchmark`

## GraphQL-Yoga

Based on `apollo-server` and `express`

1. Run server `npm run graphql-yoga`
2. Go to `localhost:3008`

Run benchmark: `npm run graphql-yoga:benchmark`
