# Задание 5. Проектирование GraphQL API

## Ключевые ресурсы и операции

### Ресурсы
- Client - (`id`, `name`, `age`).
- Document - (`id`, `type`, `number`, `issueDate`, `expiryDate`).
- Relative - (`id`, `relationType`, `name`, `age`).

### Операции
1. `GET /v1/clients/{id}`  
2. `GET /v1/clients/{id}/documents`  
3. `GET /v1/clients/{id}/relatives`  

## Схема GraphQL

[Файл со схемой](schema.graphql)

## Покрытие REST операций

1. `GET /clients/{id}`
    ```graphql
    query {
      client(id: "123") {
        id
        name
        age
      }
    }
    ```
2. `GET /clients/{id}/documents`
    ```graphql
    query {
      client(id: "123") {
        id
        name
        age
      }
    }
    ```
   или
   ```graphql
   query {
      clientDocuments(clientId: "123") {
        id
        type
        number
      }
    }
   ```
3. `GET /clients/{id}/relatives`
    ```graphql
    query {
      client(id: "123") {
        relatives {
          id
          relationType
          name
          age
        }
      }
    }
    ```
    или
    ```graphql
    query {
      clientRelatives(clientId: "123") {
        id
        relationType
        name
      }
    }
    ```