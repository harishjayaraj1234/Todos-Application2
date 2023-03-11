Given five files,

- `TodoController.java`
- `TodoRepository.java`
- `TodoH2Service.java`
- `TodoRowMapper.java`
- `Todo.java`

And also given a database file `todos` which contains `TODOLIST` table.

#### TODOLIST Table

   | Columns  |  Type   |
   | :------: | :-----: |
   |    id    | INTEGER |
   |   todo   |  TEXT   |
   |  status  |  TEXT   |
   | priority |  TEXT   |


<MultiLineNote>
Use only `TODOLIST` as a table name in your code while writing queries.

Possible values for `priority` are `HIGH`, `MEDIUM`, and `LOW`.
Possible values for `status` are `TO DO`, `IN PROGRESS`, and `DONE`.
</MultiLineNote>

### Completion Instructions

- `Todo.java`: `Todo` class should contain the following attributes.

    | Attribute |  Type  |
    | :-------: | :----: |
    |    id     |  int   |
    |   todo    | String |
    |  status   | String |
    | priority  | String |
  

- `TodoRepository.java`: Create an `interface` containing required methods.
- `TodoH2Service.java`: Update the service class with logic for managing todo data.
- `TodoController.java`: Create the controller class to  handle HTTP requests. 
- `TodoRowMapper.java`: Create a class which implements the `Rowmapper Interface`.
Implement the following APIs.

### API 1

#### Path: `/todos`

#### Method: `GET`

#### Description:

Returns a list of all `todos` in the `todoList`.

#### Response

```
[
    {
        "id": 1,
        "todo": "Watch Movie",
        "priority": "LOW",
        "status": "TO DO"
    },
   ...
]
```

### API 2

#### Path: `/todos`

#### Method: `POST`

#### Description:

Creates a new todo in the `todoList`. The `id` is auto-incremented.

#### Request

```
{
    "todo": "Read Book",
    "priority": "MEDIUM",
    "status": "TO DO"
}
```

#### Response

```
{
    "id": 6,
    "todo": "Read Book",
    "priority": "MEDIUM",
    "status": "TO DO"
}
```

### API 3

#### Path: `/todos/{id}`

#### Method: `GET`

#### Description:

Returns a todo based on the `id`. If the given `id` is not found in the `todoList`, raise `ResponseStatusException` with `HttpStatus.NOT_FOUND`.


#### Success Response

```
{
    "id": 3,
    "todo": "Buy Groceries",
    "priority": "MEDIUM",
    "status": "TO DO"
}
```

### API 4

#### Path: `/todos/{id}`

#### Method: `PUT`

#### Description:

Updates the details of a todo in the `todoList` based on the `id`. If the given `id` is not found in the `todoList`, raise `ResponseStatusException` with `HttpStatus.NOT_FOUND`.

#### Request

```
{
    "status": "DONE"
}
```

#### Success Response

```
{
    "id": 3,
    "todo": "Buy Groceries",
    "priority": "MEDIUM",
    "status": "DONE"
}
```

### API 5

#### Path: `/todos/{id}`

#### Method: `DELETE`

#### Description:

Deletes a todo from the `todoList`  based on the `id`. If the given `id` is not found in the `todoList`, raise `ResponseStatusException` with `HttpStatus.NOT_FOUND`.


**Do not modify the code in `TodoApplication.java`**

**Do not  modify anything in the `application.properties` file**

**Do not add any Sql files**