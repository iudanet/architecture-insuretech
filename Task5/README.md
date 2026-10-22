# Task5 - GraphQL API сервиса client-info

[`schema.graphql`](./schema.graphql)

| REST | GraphQL |
|---|---|
| `GET /clients/{id}` | `client(id)` |
| `GET /clients/{id}/documents` | `client(id) { documents }` |
| `GET /clients/{id}/relatives` | `client(id) { relatives }` |
