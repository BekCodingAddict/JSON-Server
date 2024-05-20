# JSON SERVER
## About:
 - json-server is a tool that allows you to create a full fake REST API with zero coding in less than 30 seconds. It's particularly useful for prototyping, front-end development, and testing without needing to set up a complex backend. json-server uses a simple JSON file as a database and generates a complete RESTful API based on that file.
## Features of json-server:
 - No coding required: Quickly create a REST API without writing any backend code.
 - CRUD operations: Automatically handles Create, Read, Update, and Delete operations.
 - Custom routes: Allows you to define custom routes for more complex scenarios.
 - Middleware: Supports middleware for adding custom behavior.
 - Real-time updates: Watches the JSON file for changes and updates the API in real-time.
## How to Set Up and Use json-server:
 - Here’s a step-by-step guide to setting up and using json-server:
   - 1. Install Node.js:
     - Make sure you have Node.js installed on your machine. You can download it from the [Node.js official website](https://nodejs.org/en).
     2.  Install json-server:
     - Install json-server globally using npm (Node Package Manager):
       - ```sh  npm install -g json-server```
     3. Create a JSON File:
     - Create a JSON file (db.json) that will act as your database. For example:
       - ```json
         {
           "posts": [
              { "id": 1, "title": "Hello World", "author": "John Doe" },
              { "id": 2, "title": "JSON Server", "author": "Jane Doe" }
           ],
          "comments": [
             { "id": 1, "postId": 1, "body": "Great post!" },
             { "id": 2, "postId": 1, "body": "Thanks for sharing." }
          ]
         }
         ```
         
