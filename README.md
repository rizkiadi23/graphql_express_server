## Simple GraphQL Server
This is a simple Express-GraphQL server that will show how to perform CRUD functionality to another service. In this example, we are using json-server as a service resource.

### Install & Try!
1. Clone this project

2. Install Project
```sh
npm install
```

3. Run GraphQL Server
```sh
npm run dev:server
```

4. Run json-server as service resource
```sh
npm run json:server
```

5. Open Browser direct to `http://localhost:4000/graphql`

6. Run the query from the GraphQL console:

- To get customer by its id copy this query to the console and run:
```sh
{
  customer(id: "1") {
    id, email, name
  }
}
```

- To get all customers, copy and run this query:
```sh
{
  customers {
    id, email, name
  }
}
```

- To create new customer to service resource (json-server) from GraphQL server, copy and run this query:
```sh
mutation {
  addCustomer(name: "Testing User", email: "test@user.com", age: 19) {
    id,
    name,
    age
  }
}

```

- To edit customer in service resource (json-server) from GraphQL server, copy and run this query:
```sh
mutation {
  editCustomer(id: "2", age: 100) {
    id,
    name,
    age
  }
}
```

- To delete customer in service resource (json-server) from GraphQL server, copy and run this query:
```sh
mutation {
  deleteCustomer(id: "5") {
    id
  }
}
```

7. Validate all data you have been created/edited/removed in 6 step with the data in `data.json` file.