# Book Review Application

This is a Book Review Application built with Node.js and Express. It allows users to register, log in, view a list of available books, and add, modify, and delete reviews for books. The application demonstrates the use of RESTful APIs and basic authentication.

## Features

- User Registration and Login
- View List of Books
- View Book Details by ISBN
- View Books by Author
- View Books by Title
- Add or Modify Book Reviews
- Delete Book Reviews

## Technologies Used

- Node.js
- Express
- Axios (for async requests)

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/venkatesh-reddi/expressBookReviews.git
    ```

2. Navigate to the project directory:

    ```bash
    cd expressBookReviews
    ```

3. Install the dependencies:

    ```bash
    npm install
    ```

## Usage

1. Start the server:

    ```bash
    node index.js
    ```

2. The application will be running on `http://localhost:3000`.

## API Endpoints

### Public Endpoints

#### Register a new user

    ```http
    POST /register
    ```

Request Body:

    ```json
    {
      "username": "yourusername",
      "password": "yourpassword"
    }
    ```

#### Get the list of books

    ```http
    GET /books
    ```

#### Get book details by ISBN

    ```http
    GET /isbn/:isbn
    ```

#### Get books by author

    ```http
    GET /author/:author
    ```

#### Get books by title

    ```http
    GET /title/:title
    ```

#### Get book reviews by ISBN

    ```http
    GET /review/:isbn
    ```

### Authenticated Endpoints

#### User Login

    ```http
    POST /login
    ```

Request Body:

    ```json
    {
      "username": "yourusername",
      "password": "yourpassword"
    }
    ```

#### Add or Modify a Book Review

    ```http
    PUT /auth/review/:isbn?review=yourreview
    ```

#### Delete a Book Review

    ```http
    DELETE /auth/review/:isbn
    ```

## Example Code

Here's an example of how to fetch the list of books using async-await with Axios:

    ```javascript
    const express = require('express');
    const axios = require('axios');
    const general = express.Router();

    const API_URL = 'https://api.example.com/books'; // Replace with your actual API URL

    // Using async-await with Axios to fetch the list of books
    general.get('/books', async (req, res) => {
      try {
        const response = await axios.get(API_URL);
        res.status(200).json(response.data);
      } catch (error) {
        res.status(500).json({ message: "Error fetching books" });
      }
    });

    module.exports.general = general;
    ```

## Contribution

Feel free to contribute to this project by opening issues and submitting pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the Apache 2.0 License.

---

Happy coding! If you have any questions or need further assistance, please don't hesitate to reach out.

---

Venkatesh Reddi

[GitHub Profile](https://github.com/venkatesh-reddi) | [LinkedIn Profile](https://linkedin.com/in/venkateshreddi)
