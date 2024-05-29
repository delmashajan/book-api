# Laravel Book Management System

## Branch Information
The main codebase is located in the `master` branch. Please ensure you are working with or referencing the correct branch.


## Description
This is a simple CRUD application built with Laravel to manage books. Users can add, view, update, and delete books. Each book has a title, author, and summary.

## Installation
To get the application up and running, follow these steps:

### Prerequisites
- PHP >= 8.0
- Composer
- MySQL
- Node.js & NPM

### Steps
1. **Clone the repository**:
    ```sh
    git clone https://github.com/delmashajan/book-api.git
    ```

2. **Navigate to the project directory**:
    ```sh
    cd book-api
    ```

3. **Checkout the `master` branch**:
    ```sh
    git checkout master
    ```
    ```

4. **Install dependencies**:
    ```sh
    composer install
    npm install
    ```

5. **Copy `.env.example` to `.env`**:
    ```sh
    cp .env.example .env
    ```

6. **Set up the database**:
    - Open the `.env` file and set your database credentials.
    ```dotenv
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=your_database_name
    DB_USERNAME=your_database_user
    DB_PASSWORD=your_database_password
    ```

7. **Generate the application key**:
    ```sh
    php artisan key:generate
    ```

8. **Run migrations**:
    ```sh
    php artisan migrate
    ```

9. **Start the development server**:
    ```sh
    php artisan serve
    ```

10. **Access the application**:
    Open Postman and use this base URL `http://127.0.0.1:8000/api`.

## Usage
Use the following endpoints to interact with the application via Postman:

- **Add a new book**: Use the POST request at `http://127.0.0.1:8000/api/books` with the required fields `title`, `author`, and `summary` in the body.
- **View all books**: Use the GET request at `http://127.0.0.1:8000/api/books` to view all books.
- **View details of a specific book**: Use the GET request at `http://127.0.0.1:8000/api/books/{id}` to view details of a specific book by providing the book's ID in the URL.
- **Update a book's details**: Use the PUT request at `http://127.0.0.1:8000/api/books/{id}` to update a book's details by providing the book's ID in the URL and the updated fields in the body.
- **Delete a book**: Use the DELETE request at `http://127.0.0.1:8000/api/books/{id}` to delete a book by providing the book's ID in the URL.

## API Documentation

Here is a brief description of the API endpoints:

### Create a Book
- **Endpoint**: `POST /api/books`
- **Description**: Adds a new book.
- **Parameters**:
    - `title` (string, required): The title of the book.
    - `author` (string, required): The author of the book.
    - `summary` (text, nullable): A brief summary of the book.

### List All Books
- **Endpoint**: `GET /api/books`
- **Description**: Retrieves a list of all books.

### Get Book Details
- **Endpoint**: `GET /api/books/{id}`
- **Description**: Retrieves the details of a specific book by ID.
- **Parameters**:
    - `id` (integer, required): The ID of the book.

### Update a Book
- **Endpoint**: `PUT /api/books/{id}`
- **Description**: Updates the details of a specific book.
- **Parameters**:
    - `id` (integer, required): The ID of the book.
    - `title` (string, optional): The new title of the book.
    - `author` (string, optional): The new author of the book.
    - `summary` (text, optional): The new summary of the book.

### Delete a Book
- **Endpoint**: `DELETE /api/books/{id}`
- **Description**: Deletes a specific book by ID.
- **Parameters**:
    - `id` (integer, required): The ID of the book.
