# Backend Template

```
## Overview

This is a reusable backend template built with TypeScript and Express.js.It provides a solid foundation for developing RESTful APIs with organized and modular code. The project includes essential components such as controllers, database connections, middleware, models, routes, and utility functions.
```

## Project Structure

```
.
├── src/
│ ├── controllers/
│ ├── database/
│ ├── middleware/
│ ├── models/
│ ├── routes/
│ ├── utils/
│ └── index.ts
├── .gitignore
├── package.json
├── tsconfig.json
└── README.md

```

- **`src/index.ts`**: Entry point for the application where the Express server is set up and connected.
- **`controllers/`**: Contains the controller files that handle the business logic of your application.
- **`database/`**: Contains files related to database connections and models.
- **`middleware/`**: Contains middleware functions used in the application (e.g., authentication, logging).
- **`models/`**: Contains database models or schemas.
- **`routes/`**: Contains route definitions and route handlers.
- **`utils/`**: Contains utility functions and helpers used across the application.

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/PremSingh24/backend-template.git
   ```

2. **Navigate to the project directory:**

   ```bash
   cd backend-template
   ```

3. **Remove the existing .git directory:**

   ```base
   rm -rf .git
   ```

   This step removes the existing Git history and configuration from the cloned repository.

4. **Reinitialize Git for your project:**

   ```base
   git init
   ```

   This command sets up a new Git repository in your project directory, allowing you to start fresh with your own version control.

5. **Install dependencies:**

   ```bash
   npm install
   ```

   This command installs all the necessary npm packages required for the project as specified in the `package.json` file.

## Usage

### Development

To start the development server with TypeScript support and automatic reloading, use:

```bash
npm run dev
```

#### How It Works:

- **`npm run dev`** uses `nodemon` to watch for changes in your TypeScript files.
- **`nodemon`** automatically restarts the server when changes are detected.
- **`ts-node/register`** is used to execute TypeScript files directly, so there's no need to compile them first.
- **`--env-file=.env`** loads environment variables from the `.env` file.

### Building

To compile TypeScript files into JavaScript, use:

```bash
npm run build
```

#### How It Works:

- **`npm run build`** uses the TypeScript compiler (`tsc`).
- The TypeScript compiler (`tsc`) generates JavaScript files in the `dist` directory, based on the configuration in `tsconfig.json`.

### Starting the Application

After building the project, you can start the application with:

```bash
npm start
```

#### How It Works:

- **`npm start`** runs the compiled JavaScript files from the `dist` directory.
- This is typically used in production environments where you want to run the optimized and compiled code.

## Configuration

### Environment Variables

You can use environment variables by placing them in the `.env` file. This file should be included in the root of your project and will be loaded when running the application.

#### Configuration in Files:

- **`nodemon.json`**:

  ```json
  {
    "watch": ["src"],
    "ext": "ts",
    "exec": "node -r ts-node/register --env-file=.env src/index.ts"
  }
  ```

- **`package.json`**:
  ```json
  {
    "scripts": {
      "start": "node --env-file=.env dist/index.js",
      "build": "tsc",
      "dev": "nodemon"
    }
  }
  ```

### Configuration Files

- **`tsconfig.json`**: This is the TypeScript configuration file that specifies compiler options and other settings for TypeScript.
- **`.gitignore`**: This file specifies which files and directories should be ignored by Git, such as `node_modules`, build artifacts, and environment files.

## Folder Descriptions

- **`controllers/`**: Place your business logic here. Each controller should manage specific routes or groups of routes and handle requests/responses.
- **`database/`**: Set up your database connection, schemas, and models. This folder includes the logic to interact with your database.
- **`middleware/`**: Implement middleware functions here, such as authentication checks, logging, or request validation.
- **`models/`**: Define database schemas or models that represent the data structure. These are used to interact with the database.
- **`routes/`**: Define your API routes and link them to the appropriate controllers. This folder organizes route handling and route definitions.
- **`utils/`**: Create utility functions or helper methods that can be reused across the application. This might include things like validation functions or custom error handlers.

## Contributing

If you’d like to contribute to this project, please follow these steps:

1. **Fork the repository.**
2. **Create a new branch:**

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes and commit:**

   ```bash
   git add .
   git commit -m "Add your commit message"
   ```

4. **Push to the branch:**

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Create a Pull Request.**

   Go to the repository on GitHub and open a Pull Request from your branch. Provide a clear description of the changes and submit the request for review.
