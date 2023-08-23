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
      - cors: A middleware for handling Cross-Origin Resource Sharing (CORS) to enable or restrict access to your API from different domains. See MIDDLEWARE below;
      - dotenv: Loads environment variables from a .env file into process.env, making it easier to manage configuration settings.
      - gridfs-stream: A library for working with GridFS, a specification for storing large files (e.g. images, videos) in MongoDB.
      - multer: Middleware for handling multipart/form-data, commonly used for uploading files in forms. See (a) MULTIPART/FORM-DATA below.
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





(a) MULTIPART/FORM-DATA

multipart/form-data is a content type used in HTTP requests to send binary data, like files, as part of a form submission. When a user uploads files through a web form on a website, such as images, videos, or documents, these files are typically sent using the multipart/form-data encoding. This allows the browser to send not only text-based form data but also binary data like files.

In a multipart/form-data request, the binary data is divided into multiple parts, each with its own content type and headers. These parts are separated by a boundary string that is specified in the request headers. Each part contains a Content-Disposition header that provides information about the name of the input field and the filename of the uploaded file.

This encoding is used because traditional URL-encoded form data (application/x-www-form-urlencoded) is not suitable for sending binary files due to limitations in character encoding. multipart/form-data allows the data to be transmitted efficiently without altering the binary content.

Libraries like multer in Node.js make it easier to handle multipart/form-data requests by parsing the incoming data and providing a convenient interface to access the uploaded files and other form fields.

(b) HASHING AND SALTING PASSWORDS

Hashing and salting are security practices used to protect passwords and enhance their security in systems that require user authentication. They are particularly important to mitigate the risks associated with data breaches and unauthorized access.

    Hashing:
    Hashing involves transforming a password (or any input) into a fixed-length string of characters using a mathematical function called a hash function. Hash functions are designed to be one-way, meaning that it is computationally infeasible to reverse the process and retrieve the original input from the hash value. This makes it difficult for attackers to obtain the actual passwords even if they manage to access the hashed values.

When a user creates or updates their password, the system hashes the password and stores only the hash value in the database, not the actual password. When the user tries to log in, the system hashes the entered password and compares the resulting hash value with the stored hash. If they match, the password is considered correct.

    Salting:
    A salt is a random value that is generated for each user and combined with their password before hashing. The salt is then stored along with the hash value in the database. Salting helps prevent attackers from using precomputed tables (rainbow tables) to quickly guess the original password based on common hash values.

The primary purpose of salting is to add uniqueness to each hashed password, even if two users have the same password. This means that even if two users have the same password, their hash values will be different due to the different salts. As a result, rainbow table attacks become ineffective because the attacker would need to compute tables for each possible salt.

In summary, the purpose of hashing and salting passwords is to:

    Protect the actual passwords in case of a data breach: Even if an attacker gains access to the hashed passwords, they would be extremely difficult to reverse engineer.
    Prevent the use of precomputed tables: Salting makes it much more difficult for attackers to use precomputed tables of hash values to quickly guess passwords.
    Add an extra layer of security: Salting adds randomness to the hash process, making it harder for attackers to predict the hash output.

Modern security practices also involve using strong, slow hash functions (such as bcrypt or Argon2) that make brute-force attacks more difficult and time-consuming. Combining these techniques helps ensure a higher level of security for user passwords and sensitive data.

(c) MIDDLEWARE
Middleware is a concept used in software development, particularly in the context of web applications, to describe a set of functions or code that sits between different components of a system and adds certain functionality to the application's behavior or processing flow. Middleware acts as a bridge or a layer that intercepts requests, responses, or other data as they move between different parts of an application.

The primary purposes of middleware are:

1. **Modularity and Reusability**: Middleware allows developers to break down complex systems into smaller, manageable pieces of code that can be reused across different parts of an application. This modularity makes code easier to maintain and enhances the overall development process.

2. **Cross-Cutting Concerns**: Cross-cutting concerns are aspects of an application that affect multiple components, such as logging, authentication, security, and error handling. Middleware can be used to implement and manage these concerns consistently across different parts of the application.

3. **Request and Response Manipulation**: Middleware can intercept incoming requests and outgoing responses, allowing developers to modify, enhance, or validate data before it reaches its intended destination. For example, parsing request bodies, adding headers, or transforming response data are common tasks performed by middleware.

4. **Chaining and Order**: Middleware can be organized in a specific order or sequence, forming a chain. Each middleware function in the chain can modify the request or response before passing it to the next middleware or the final handler. This allows for step-by-step processing of data.

5. **Decoupling**: Middleware enables decoupling of components, meaning that different parts of an application can operate independently of one another while still communicating through the middleware layer.

In the context of web applications, especially those built using frameworks like Express.js for Node.js, middleware is often used to perform tasks such as authentication, authorization, logging, input validation, and more. These tasks are essential for the proper functioning and security of an application but are not directly related to the core business logic. By using middleware, developers can keep their application code cleaner, more organized, and easier to maintain.

In summary, middleware acts as an intermediary layer that enhances an application's functionality by providing a way to add common behaviors, manage cross-cutting concerns, and manipulate data during its journey through different parts of the system.