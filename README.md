# E-Commerce Back End

## Description

This project is the back end for an e-commerce website. It provides a functional Express.js API with Sequelize for interacting with a MySQL database. The API supports various CRUD operations for managing categories, products, and tags.

[Walkthrough Video](https://youtu.be/vYODt6g6AdM)

## Table of Contents

- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [API Routes](#api-routes)
- [Database Models](#database-models)
- [Associations](#associations)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Technologies Used

- Express.js
- Sequelize
- MySQL
- dotenv

## Installation

1. Clone the repository.
2. Navigate to the project's root directory in the terminal.
3. Run `npm install` to install the required dependencies.
4. Set up your MySQL database and update the `.env` file with your database name, username, and password.

## Usage

1. Run `npm run seed` to seed the database with test data.
2. Start the server using `npm start`.
3. Use a tool like Insomnia to test the API routes.

## API Routes

- **GET Routes:**

  - `/api/categories`: Get all categories with associated products.
  - `/api/categories/:id`: Get a single category by ID with associated products.
  - `/api/products`: Get all products with associated categories and tags.
  - `/api/products/:id`: Get a single product by ID with associated category and tags.
  - `/api/tags`: Get all tags with associated products.
  - `/api/tags/:id`: Get a single tag by ID with associated products.

- **POST Routes:**

  - `/api/categories`: Create a new category.
  - `/api/products`: Create a new product with associated category and tags.
  - `/api/tags`: Create a new tag.

- **PUT Routes:**

  - `/api/categories/:id`: Update a category by ID.
  - `/api/products/:id`: Update a product by ID with associated category and tags.
  - `/api/tags/:id`: Update a tag by ID.

- **DELETE Routes:**
  - `/api/categories/:id`: Delete a category by ID.
  - `/api/products/:id`: Delete a product by ID.
  - `/api/tags/:id`: Delete a tag by ID.

## Database Models

- **Category:**

  - `id`: Integer, Primary Key, Auto Increment.
  - `category_name`: String, Not Null.

- **Product:**

  - `id`: Integer, Primary Key, Auto Increment.
  - `product_name`: String, Not Null.
  - `price`: Decimal, Not Null.
  - `stock`: Integer, Not Null, Default: 10.
  - `category_id`: Integer, References Category Model.

- **Tag:**

  - `id`: Integer, Primary Key, Auto Increment.
  - `tag_name`: String.

- **ProductTag:**
  - `id`: Integer, Primary Key, Auto Increment.
  - `product_id`: Integer, References Product Model.
  - `tag_id`: Integer, References Tag Model.

## Associations

- Product belongs to Category.
- Category has many Products.
- Product belongs to many Tags (through ProductTag).
- Tag belongs to many Products (through ProductTag).

## Testing

Use a tool like Insomnia to test the various API routes. Make sure to check the provided walkthrough video for a demonstration.

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

## License

This project is licensed under the [MIT License](LICENSE).
