# Exploring HTTP methods with a Car API

In this project we will create our own Car API, using the HTTP methods **GET**, **POST**, **PUT**, **DELETE**

We will also be working with request parameters and responding with the correct HTTP response status codes.

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

You can choose what properties your object will contain, but at the very least it should have an **id** and a **name**.

#### Example

```javascript
const cars = [
  { id: 1, name: "Volvo" },
  { id: 2, name: "BMW" },
  { id: 3, name: "Audi" },
];
```

### Task 4 - Add a route for a GET request to '/api/cars'

Create a **GET** endpoint for the path `/api/cars`. This should return a json `response` with the list of cars and a status code **200**.

### Task 5 - Add a route for a GET request to 'api/cars/:id'

Create a **GET** endpoint for the path `/cars/:id`.

This should;

- Return a json `response` with a car by parameter id and
- A status code **200**

But;

- If a faulty id parameter was supplied, it should return status code **400** (Bad Request)
- If an id was supplied but it can't be found in the array return status code **404**

### Task 6 - Add a route for a POST request to 'api/cars/add'

Create a **POST** endpoint for the path `api/cars/add`.

It should;

- Add a car object to the array of cars
- Return a json `response` with the newly added car object and status code **200**
- The body of the request can look like the example below;

```json
{
  "id": "4",
  "name": "Renault"
}
```

### Task 7 - Add a route for a PATCH request to 'api/cars/update/:id'

Create a **PATCH** endpoint for the path `api/cars/update/:id`.

It should;

- Find (using the id) and update an existing car in the array
- Return a json `response` with the list of cars (including the newly added one)
- A status code of **200**

But;

- If a faulty id parameter was supplied it should return status code **400** (Bad Request).
- If an id was supplied but it can't be found in the array return status code **404**.

### Task 8 - Add a route for a DELETE request to 'api/cars/delete/:id'

Create a **DELETE** endpoint for the path `api/cars/delete/:id`.

This should;

- Find (using the id) and delete the car
- Return a json `response` with the list of cars (excluding the car that was deleted)
- A status code **200**

But;

- If a faulty id paramater was supplied it should return status code **400** (Bad Request).
- If an id was supplied but it can't be found in the array return status code **404**.
