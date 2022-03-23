# Create a Cars API

In this project we will create our own Cars API, using the HTTP methods GET, POST, PUT, DELETE

We will also be responding with the correct response codes

## What you will be doing

This project will allow you to practise using:

> HTTP methods and response codes

This project assumes you've already had experience with:

> - Express basic setup
> - Javascript Arrays

## Tasks

For these tasks, you are expected to write your code in the file `server.js`

### Task 1 - Getting ready

1. Initialise npm into your project
   `npm init -y`
2. Set the `package.json` type to module
3. Install the express.js npm package
   `npm i express`
4. Create a file for your server (`server.js`)

### Task 2 - Set up your server

> Boilerplate

```javascript
import express from "express";
const app = express();

app.use(express.urlencoded({ extended: true }));
app.use(express.json());

app.listen(3000, () => {
  console.log("The server is listening");
});
```

### Task 3 - Initialize an array of car objects

1. Initialize an array of car objects, you can choose how you form your objects

```javascript
const cars = [
  { id: 1, name: "Volvo" },
  { id: 2, name: "BMW" },
  { id: 3, name: "Audi" },
];
```

### Task 4 - Add a route for a GET request to '/api/cars'

Write a controller that will respond to the path `/api/cars`. This should return a json `response` with the list of cars and a status code 200.

### Task 5 - Add a route for a GET request to 'api/cars/:id'

Write a controller that will respond to the path `/cars/:id`. This should return a json `response` with a car by parameter id and a status code 200.

- If a faulty id parameter was supplied it should return status code 400 (Bad Request).
- If an id was supplied but it can't be found in the array return status code 404.

### Task 6 - Add a route for a POST request to 'api/cars/add'

Write a controller that will respond to a post request to the path `api/cars/add`.
A car object should be added to the array of cars. This should return a json `response` with the added car object and status code 200. The body of the request can look like this and should contain the necessary fields to create the new car object:

```json
{
  "id": "4",
  "name": "Renault"
}
```

### Task 7 - Add a route for a PATCH request to 'api/cars/update/:id'

Write a controller that will respond to the path `api/cars/update/:id`. This should update an existing car and return a json `response` with the list of cars (including the newly added one) and a status code 200.

- If a faulty id parameter was supplied it should return status code 400 (Bad Request).
- If an id was supplied but it can't be found in the array return status code 404.

### Task 8 - Add a route for a DELETE request to 'api/cars/delete/:id'

Write a controller that will respond to the path `api/cars/delete/:id`. This should delete the car by id and should return a json `response` with the list of cars (excluding the car that was deleted) and a status code 200.

- If a faulty id paramater was supplied it should return status code 400 (Bad Request).
- If an id was supplied but it can't be found in the array return status code 404.
