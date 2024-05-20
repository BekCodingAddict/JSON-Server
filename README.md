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
   - * Install Node.js:
     - Make sure you have Node.js installed on your machine. You can download it from the [Node.js official website](https://nodejs.org/en).
     2.  Install json-server:
     - Install json-server globally using npm (Node Package Manager):
       - ```sh
            npm install -g json-server
         ```
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
      4. Start json-server:
      - Run the json-server with the following command:
        - ```sh
          json-server --watch db.json
          ```
        - This command starts a server and watches the db.json file for changes. By default, json-server 
          runs on port 3000. You can access your API at http://localhost:3000.
       5. Using the API:
       - With the server running, you can perform CRUD operations on your JSON data. Here are some example API endpoints:
         - GET /posts: Fetch all posts.
         - GET /posts/1: Fetch the post with id 1.
         - POST /posts: Add a new post.
         - PUT /posts/1: Update the post with id 1.
         - DELETE /posts/1: Delete the post with id 1.
       6. Custom Routes:
       - You can create a custom routes file to define more complex routing. Create a routes.json file:
         - ```json
           {
             "/api/": "/",
             "/api/posts/:id": "/posts/:id"
           }
         - Then, start the json-server with the routes file:
           - ```sh
             json-server --watch db.json --routes routes.json
             ```
        7. Middleware and Customization:
        - You can add custom middleware to json-server for additional functionality. Create a server.js file:
          - ```js
            const jsonServer = require('json-server');
            const server = jsonServer.create();
            const router = jsonServer.router('db.json');
            const middlewares = jsonServer.defaults();

            // Custom middleware example
            server.use((req, res, next) => {
              if (req.method === 'POST') {
              req.body.createdAt = Date.now();
            }
              next();
            });

            server.use(middlewares);
            server.use(router);

            server.listen(3000, () => {
            console.log('JSON Server is running on http://localhost:3000');
            });
            ```
          - Run the server using Node.js:
            - ```sh
              node server.js
              ```
        8. Conclusion:
        - json-server is a powerful and easy-to-use tool for creating a mock REST API. It is ideal for:
          - Prototyping and rapid development.
          - Building front-end applications without a real backend.
          - Testing and debugging front-end code.
        - By following the steps above, you can quickly set up a functional REST API based on a simple JSON file, allowing you to focus on developing and testing your front-end applications.





          
         
