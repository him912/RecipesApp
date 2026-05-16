# Recipes App

A REST API application for managing recipes using Node.js, Express.js, and MongoDB.

## Features
- Create Recipe
- Get All Recipes
- Get Recipe By ID
- Update Recipe
- Delete Recipe

## Tech Stack
- Node.js
- Express.js
- MongoDB
- Mongoose

📬 Postman Documentation

🌐 API Base URL 
https://recipesapp-tlhz.onrender.com/api/recipes

📮 API Endpoints
Method	Endpoint	Description
POST	/api/recipes	Create Recipe
GET	/api/recipes	Get All Recipes
GET	api/recipes/:id	Get Recipe By ID
PUT	/api/recipes/:id	Update Recipe
DELETE	/api/recipes/:id	Delete Recipe

Create Recipe API
Endpoint
POST /api/recipes
Description
This API creates a new recipe and stores it in MongoDB.

Request Body

JSON

{
  "title": "Paneer Butter Masala",
  "ingredients": ["Paneer", "Butter", "Tomato"],
  "instructions": "Cook all ingredients together",
  "cookingTime": 30
}


Success Response


JSON

{
  "success": true,
  "message": "Recipe created successfully",
  "data": {
    "_id": "6825abcd123456789",
    "title": "Paneer Butter Masala",
    "ingredients": ["Paneer", "Butter", "Tomato"],
    "instructions": "Cook all ingredients together",
    "cookingTime": 30
  }
}

Error Response

JSON

{
  "success": false,
  "message": "Recipe title is required"
}


Get All Recipes API
Endpoint
GET /api/recipes
Description
This API retrieves all recipes stored in MongoDB.
Success Response

JSON
{
  "success": true,
  "count": 2,
  "data": [
    {
      "_id": "6825abcd123456789",
      "title": "Paneer Butter Masala",
      "ingredients": ["Paneer", "Butter", "Tomato"],
      "instructions": "Cook all ingredients together",
      "cookingTime": 30
    },
    {
      "_id": "6825efgh987654321",
      "title": "Veg Biryani",
      "ingredients": ["Rice", "Vegetables", "Spices"],
      "instructions": "Cook rice with vegetables and spices",
      "cookingTime": 45
    }
  ]
}


Error Response

JSON
{
  "success": false,
  "message": "Internal server error"
}

Get Recipe By ID API
Endpoint
GET /api/recipes/:id
Description
This API retrieves a single recipe using its MongoDB ObjectId.
Example URL


Bash

GET /api/recipes/6825abcd123456789

Success Response

JSON
{
  "success": true,
  "data": {
    "_id": "6825abcd123456789",
    "title": "Paneer Butter Masala",
    "ingredients": ["Paneer", "Butter", "Tomato"],
    "instructions": "Cook all ingredients together",
    "cookingTime": 30
  }
}

Error Response

JSON

{
  "success": false,
  "message": "Recipe not found"
}

Update Recipe API
Endpoint
PUT /api/recipes/:id
Description
This API updates an existing recipe by ID.
Example URL


Bash

PUT /api/recipes/6825abcd123456789

Request Body

JSON

{
  "title": "Updated Paneer Recipe",
  "cookingTime": 40
}

Success Response

JSON

{
  "success": true,
  "message": "Recipe updated successfully",
  "data": {
    "_id": "6825abcd123456789",
    "title": "Updated Paneer Recipe",
    "ingredients": ["Paneer", "Butter", "Tomato"],
    "instructions": "Cook all ingredients together",
    "cookingTime": 40
  }
}


Error Response

JSON

{
  "success": false,
  "message": "Recipe not found"
}

Delete Recipe API
Endpoint
DELETE /api/recipes/:id

Description
This API deletes a recipe from MongoDB using its ID.
Example URL


Bash

DELETE /api/recipes/6825abcd123456789

Success Response

JSON

{
  "success": true,
  "message": "Recipe deleted successfully"
}

Error Response

JSON
{
  "success": false,
  "message": "Recipe not found"
}

