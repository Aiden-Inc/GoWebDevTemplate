# Go Web Development Template with TypeScript, Vite, React, and SQLite3

This web development template is designed to streamline the process of building full-stack applications using Go for the backend and TypeScript, Vite, and React for the frontend. The template comes preconfigured with Docker for easy deployment and integrates SQLite3 as the database for lightweight, server-side storage.
## Key Features:

- Backend (Go): The backend of the application is built using Go, which provides a fast and efficient foundation for serving APIs, handling business logic, and managing data.
- Frontend (TypeScript, Vite, React): The frontend uses TypeScript for type safety, Vite for fast builds and development experience, and React for a flexible, component-driven user interface.
- SQLite3: The backend generates and interacts with an SQLite3 database file, providing a simple yet robust storage solution for your application.
- Docker Deployment: The entire application stack is Dockerized, ensuring that the app runs consistently across different environments with minimal setup.
- Development Setup: The template comes with a simple structure that allows you to focus on your application logic rather than configuration.

## Folder Structure:
```
/my-app
│
├── backend/
│   └── main.go                # Go server (handles routes, API logic, SQLite interaction)
│   └── go.mod                 # Go module dependencies
│   └── database/
│       └── db.go              # Database connection and queries for SQLite3
│
├── frontend/
│   └── src/
│       └── App.tsx            # Main React component
│       └── index.tsx          # React entry point
│       └── components/        # Reusable UI components
│   └── package.json           # NPM dependencies and scripts
│   └── vite.config.ts         # Vite configuration for bundling and development
│
├── docker-compose.yml         # Docker Compose configuration for backend and frontend
└── Dockerfile                 # Dockerfile for backend
└── README.md                  # Project overview and setup instructions
```
## How It Works:

- Backend (Go):
    - The Go backend provides APIs that interact with the SQLite3 database. It is designed to serve RESTful endpoints that can be consumed by the frontend.
    - The main.go file sets up the HTTP server, handles routing, and connects to the SQLite3 database.
    - The database/db.go file is where the database connection and queries are managed.

- Frontend (TypeScript, Vite, React):
    - The frontend uses React components, written in TypeScript, which ensures type safety and maintainability.
    - Vite is used for fast development builds, hot-reloading, and optimized production builds. The frontend communicates with the Go backend via REST APIs.
    - The vite.config.ts file configures Vite for the development environment, including paths, optimizations, and plugin setups.

- SQLite3 Database:
    - The application uses SQLite3 to store application data. The database is lightweight and file-based, making it ideal for small to medium applications.
    - The Go backend interacts with SQLite3 using Go’s database/sql package and an SQLite driver (e.g., github.com/mattn/go-sqlite3).
    - The database file is generated dynamically and can be found in the backend directory, making it easy to manage and move around.

- Docker Deployment:
    - Docker is used to containerize both the backend and frontend applications, ensuring that they run in isolated environments.
    - The docker-compose.yml file is used to define the services (backend and frontend) and their dependencies.
    - The Dockerfile for the backend specifies how to build the Go application and its environment, while the frontend is handled by Vite and NPM inside the container.

## Deployment Instructions:

- Clone the repository or download the template.

- Run the following command to start the development environment:

- docker-compose up --build

- This will build the Docker containers for both the frontend and backend and start them.

- Navigate to `http://localhost:5173/` in your browser to see the application in action.

- To run the application in production, you can build and deploy the Docker containers to your preferred cloud provider.

## Customization:

- Backend: Modify the main.go file to add new routes and business logic. You can extend the SQLite3 interaction by adding more models and queries.
- Frontend: Update React components in the frontend/src/components directory. Add new pages or features as needed.
- Database: If you need to extend the database schema, you can modify the db.go file and add migration logic.

## Conclusion:

This template is perfect for developers who need a simple, yet powerful, starting point for building modern web applications with Go and TypeScript. It combines the speed of Go with the flexibility of React and the simplicity of SQLite3, all packaged in a Docker container for easy deployment.
