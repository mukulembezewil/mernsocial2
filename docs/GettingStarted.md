1. Install node.js from nodejs.org
2. Install npx so we can run npx commands
      - first check if npx is already installed; run
        - which npx
        - npx -v
      - install npx
        - npm i npx
  {On npx: https://www.freecodecamp.org/news/npm-vs-npx-whats-the-difference/}

3. Create a project folder
      - Create a subfolder called server => mkdir server
      - Change directory into the folder => cd server
      - Install nodemon if not yet already installed on yor machine => npm i -g nodemon

  {nodemon: Nodemon is a command-line tool that helps with the speedy development of Node. js applications. It monitors your project directory and automatically restarts your node application when it detects any changes. This means that you do not have to stop and restart your applications in order for your changes to take effect.}

4. Install the following:
    => npm i express body-parser bcrypt cors dotenv gridfs-stream multer multer-gridfs-storage helmet morgan jsonwebtoken mongoose
      - express: A web application framework for Node.js used to create APIs and handle HTTP requests and responses.
      - body-parser: Middleware for parsing the request body data, especially useful for handling form data and JSON payloads.
      - bcrypt: A library for hashing and salting passwords, often used for securely storing user passwords.
      - cors: A middleware for handling Cross-Origin Resource Sharing (CORS) to enable or restrict access to your API from different domains.
      - dotenv: Loads environment variables from a .env file into process.env, making it easier to manage configuration settings.
      - gridfs-stream: A library for working with GridFS, a specification for storing large files (e.g. images, videos) in MongoDB.
      - multer: Middleware for handling multipart/form-data, commonly used for uploading files in forms.
      - multer-gridfs-storage: An extension for Multer that allows you to store uploaded files directly in GridFS
      - helmet: A package for adding security-related HTTP headers to enhance the security of your Express application.
      - morgan: A logging middleware that helps you log incoming HTTP requests to your server, useful for debugging and monitoring.
      - jsonwebtoken: A library for creating and verifying JSON Web Tokens (JWTs), often used for user authentication and authorization.
      - mongoose: An Object Data Modeling (ODM) library for MongoDB and Node.js, simplifying the interaction with MongoDB providing a schema-based approach.
    These packages collectively provide a solid foundation for building web applications with Node.js and Express, including handling routes, user authentication, security, database interactions and more.

5. Run one more command while in server directory in terminal
      - npm init -y
6. In the package.json add the property
      - "type": "module
     {This allows you to use import statement rather than require.}    
7.  Add an index.js file to the server directory.