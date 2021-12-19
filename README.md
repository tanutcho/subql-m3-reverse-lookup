# SubQuery - Module 3 - Lesson 3 -Reverse Lookup Balances Transfer

One to Many entities example from SubQuery Hero Course

This package is the example of Account Transfer data which shown ID of account (from), amount and end-account (to) 

Extended with Reverse Lookup Entity
## Preparation

#### Environment

- [Typescript](https://www.typescriptlang.org/) are required to compile project and define types.  

- Both SubQuery CLI and generated Project have dependencies and require [Node](https://nodejs.org/en/).
     

#### Install the SubQuery CLI

Install SubQuery CLI globally on your terminal by using NPM:

```
npm install -g @subql/cli
```

Run help to see available commands and usage provide by CLI
```
subql help
```

## Initialize the project

under the project directory, run following command to install all the dependency.
```
yarn install
```

#### Code generation

In order to index your SubQuery project, it is mandatory to build your project first.
Run this command under the project directory.

````
yarn codegen
````

## Build the project

In order to deploy your SubQuery project to our hosted service, it is mandatory to pack your configuration before upload. You need to build it

```
yarn build
```

## Indexing and Query

#### Run required systems in docker


Under the project directory run following command:

```
docker-compose pull && docker-compose up
```
#### Query the project

Open your browser and head to `http://localhost:3000`.

Finally, you should see a GraphQL playground is showing in the explorer and the schemas that ready to query.

You can try this for getting first 5 transfer transactions

````graphql
query {
  accounts(first: 5) {
    nodes {
      id
      myToAddress{
        nodes{
          id
          amount
        }
      }
    }
  }
}

````
