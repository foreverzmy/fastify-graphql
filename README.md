# fastify-graphql
<div>
  <img src="https://travis-ci.org/sirsavary/fastify-graphql.svg?branch=master">
</div>

## Install
```bash
npm install --save fastify-apollo graphql
```

## Register Plugins
```js
const Fastify = require('fastify');
const app = Fastify();

const {graphiqlFastify, graphqlFastify} = require('fastify-graphql');
app.register(graphqlFastify, { 
  prefix: '/graphql', 
  graphql: {
    schema: your_graphql_schema,
  },
});
app.register(graphiqlFastify, {
  prefix: '/graphiql',
  graphiql: {
    endpointURL: '/graphql',
  }
});
```

## Configuration

Both plugins need to be given a prefix, under which they will mount.

GraphQL settings extends [GraphQLServerOptions](https://github.com/apollographql/apollo-server/blob/master/packages/apollo-server-core/src/graphqlOptions.ts#L7-L16)

GraphiQL settings extends [GraphiQLData](https://github.com/apollographql/apollo-server/blob/master/packages/apollo-server-module-graphiql/src/renderGraphiQL.ts#L9-L29)
