# Fastify Starter Test

[origin repo url](https://github.com/jellydn/fastify-starter)

## Features

- Swagger documentation generator for Fastify https://github.com/fastify/fastify-swagger
- Generates swagger/openapi specification based on jsDoc comments and YAML files. https://github.com/Surnet/swagger-jsdoc
- Mercurius is a GraphQL adapter for Fastify https://mercurius.dev/
- Code-GraphQL Nexus
  Declarative, Code-First GraphQL Schemas for JavaScript/TypeScript https://nexusjs.org
- And some useful plugins as https://github.com/fastify/fastify-env, https://github.com/fastify/fastify-cors, https://github.com/fastify/fastify-helmet

## Install

```sh
yarn install
```

## Usage

```sh
yarn start
```

## Swagger UI

Open below link on your browser with localhost
http://localhost:3000/documentation or try with demo server https://fastify-starter.fly.dev/documentation

![https://gyazo.com/6cf6c02cb36f9d4fababdde1ad071aba.gif](https://gyazo.com/6cf6c02cb36f9d4fababdde1ad071aba.gif)

## GraphQL Client IDE

Open below link on your browser with localhost
http://localhost:3000/altair or try with demo server https://fastify-starter.fly.dev/altair

![https://gyazo.com/49e9af06a6a13390abefd5c58a1296f7.png](https://gyazo.com/49e9af06a6a13390abefd5c58a1296f7.png)

## GraphQL

If you are new to GraphQL, please watch the below video for more information.
[![IT Man - Talk #27 - GraphQL 2022 Report Insights [Vietnamese]](https://i.ytimg.com/vi/_wmldiEdwPM/hqdefault.jpg)](https://www.youtube.com/watch?v=_wmldiEdwPM)

Run below command in your terminal/CLI

```sh
curl -H "Content-Type:application/graphql" -XPOST -d "query { hello }" http://localhost:3000/graphql | jq .
```

Output:

```
{
  "data": {
    "hello": "Hello World!"
  }
}
```

## Run tests

```sh
yarn test
```

## Deployment

This template comes with two GitHub Actions that handle automatically deploying your app to production environment.

Prior to your first deployment, you'll need to do a few things:

- [Install Fly](https://fly.io/docs/getting-started/installing-flyctl/)

- Sign up and log in to Fly

  ```sh
  fly auth signup
  ```

- Create a new app on Fly:

  ```sh
  fly create fastify-starter
  ```

- Create a new [GitHub Repository](https://repo.new)

- Add a `FLY_API_TOKEN` to your GitHub repo. To do this, go to your user settings on Fly and create a new [token](https://web.fly.io/user/personal_access_tokens/new), then add it to [your repo secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets) with the name `FLY_API_TOKEN`.

Now that every is set up you can commit and push your changes to your repo. Every commit to your `main` branch will trigger a deployment to your production environment.

## GitHub Actions

We use GitHub Actions for continuous integration and deployment. Anything that gets into the `main` branch will be deployed to production after running tests/build/etc.

