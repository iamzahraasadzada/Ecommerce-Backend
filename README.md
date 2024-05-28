# README

## Overview
This project is a basic Express.js application that connects to a MySQL database to perform CRUD (Create, Read, Update, Delete) operations on a `products` table. The server is configured to handle CORS requests from specified origins and listens on port 4000.

## Prerequisites
Before running this project, ensure you have the following installed:
- Node.js
- MySQL

## Installation
1. Clone the repository:
   ```sh
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```sh
   cd <project-directory>
   ```
3. Install the required dependencies:
   ```sh
   npm install
   ```

## Configuration
Update the database connection details in the code as per your MySQL setup:
```javascript
const connection = mysql.createConnection({
  host: "localhost",
  port: 3306,
  user: "root",
  password: "0078Ziruli",
  database: "salinka",
});
```

## Running the Server
To start the server, run:
```sh
node <filename>.js
```
Replace `<filename>` with the name of your JavaScript file containing the code.

The server will start on port 4000. If there's any error during startup, it will be logged to the console.

## API Endpoints
### Get All Products
**Endpoint:** `GET /products`

**Description:** Fetches all products from the database.

**Response:**
- 200: Returns a JSON array of products.
- 500: Internal Server Error.

### Get Product by ID
**Endpoint:** `GET /products/:id`

**Description:** Fetches a single product by its ID.

**Response:**
- 200: Returns a JSON object of the product.
- 404: Product not found.
- 500: Internal Server Error.

### Create a New Product
**Endpoint:** `POST /products`

**Description:** Adds a new product to the database.

**Request Body:**
- `name`: Name of the product.
- `brand`: Brand of the product.
- `price`: Price of the product.
- `img`: Image URL of the product.

**Response:**
- 200: Returns the updated list of products.
- 500: Internal Server Error.

### Delete a Product
**Endpoint:** `DELETE /products`

**Description:** Deletes a product by its ID.

**Request Body:**
- `id`: ID of the product to delete.

**Response:**
- 200: Returns the updated list of products.
- 500: Internal Server Error.

## CORS Configuration
The server allows CORS requests from `http://localhost:5173` and `http://localhost:5174` with the methods `GET`, `POST`, `PUT`, `DELETE`, and `OPTIONS`. Adjust the `corsOptions` in the code if you need to change these settings.

```javascript
const corsOptions = {
  origin: ["http://localhost:5173", "http://localhost:5174"],
  methods: ["GET", "POST", "PUT", "DELETE", "OPTIONS"],
  allowedHeaders: ["Content-Type", "Authorization"],
};
```

## Troubleshooting
- Ensure your MySQL server is running and accessible with the provided credentials.
- Check for syntax errors or missing dependencies.
- Verify the database `salinka` and table `products` exist in your MySQL setup.

## Contributions
Feel free to fork the project and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is open-source and available under the [MIT License](LICENSE).

---
