# NestJS Backend Development Exercise

## Objective:
Develop a RESTful service for a simple Todo application using the NestJS framework. Your service will interact with a simple JSON store instead of a traditional database.

## Requirements:

### Setup and Initialization:
- Initialize a new NestJS project.
- Install `node-json-db` as an npm package for your data storage. You can find the package here: [node-json-db npm package](https://www.npmjs.com/package/node-json-db).
- Install `uuid` for generating random IDs. You can find the package here: [uuid](https://www.npmjs.com/package/uuid).
- Set up the necessary modules and services in NestJS.

### Data Structure:
- Create two entities: `Task` and `Category`.
- The `Task` entity should have fields such as `id`, `title`, `status`, and `description`, status should be an enum with values `DONE`, `IN_PROGRESS`, and  `OPEN`, and when adding task by default status should be `OPEN`. Also, add a foreign key reference to the `Category` entity.
- The `Category` entity should include fields like `id` and `name`.
- Establish a relationship between `Task` and `Category` (e.g., one `Category` can have multiple `Tasks`).

### Architecture Components:
- **Controllers**: Create controllers for handling HTTP requests. Each controller should correspond to an entity (e.g., `TasksController`, `CategoriesController`).
- **Services**: Implement services that contain business logic. These services will be used by controllers.
- **Repository**: Develop a repository layer to handle tasks related to the JSON store.

### API Endpoints:
- Implement the following RESTful endpoints:
  - `GET /tasks`: Retrieve all tasks.
  - `GET /tasks/:id`: Retrieve a single task by ID.
  - `POST /tasks`: Create a new task.
  - `DELETE /tasks/:id`: Delete a task by ID.
  - `GET /categories`: Retrieve all categories.
  - `POST /categories`: Create a new category.
  - `DELETE /categories/:id`: Delete a category by ID.

### Data Validation and Error Handling:
- Implement data validation for the incoming requests. Ensure that all required fields are provided and valid.
- Implement appropriate error handling for different scenarios like invalid requests, server errors, and non-existing resources.

### Testing
Use tools like Postman or Insomnia to test the API endpoints for each CRUD operation.

## Final Test for the Service:
To evaluate your service, perform the following steps:
1. **Create a Category:** Use the `POST /categories` endpoint to create at least one category.
2. **Create a Task and Assign Category:** Use the `POST /tasks` endpoint to create a task and assign the previously created category to it.
3. **Attempt to Delete Category:** Try to delete the category using the `DELETE /categories/:id` endpoint. This should fail and return an HTTP error, as there are tasks referring to that category. Ensure that your service returns the appropriate HTTP error (HTTP 409 Conflict).
   
## After you are done with all the functionalities:

1. **Use `Swagger` to document your API, [link](https://rehmat-sayany.medium.com/integrating-swagger-with-nestjs-a-step-by-step-guide-abd532743c43)** 
2. **Write tests for task and category controllers and services** 
