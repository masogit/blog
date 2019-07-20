
git clone https://github.com/apollographql/fullstack-tutorial/


Publish your schema
Publishing your schema gives you the power to track and manage changes in the schema over time. To publish your schema, start by creating an .env file at the root of the project with your ENGINE_API_KEY.

// .env
```
ENGINE_API_KEY=service:masogit-2523:L4vz7A2ZZWquY-2L84qq9A
```
Then start your GraphQL server and run the following command:
```
$ npx apollo service:push \
--endpoint=<your graphql endpoint here>
```
Your schema's information will show up here as soon as you upload it. See our docs for other options to provide the schema if your graphql endpoint isn't publicly available, or has disabled introspection.
