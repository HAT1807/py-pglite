# py-pglite: A Lightweight PostgreSQL Wrapper for Python

![PGlite Logo](https://img.shields.io/badge/PGlite-Python%20Wrapper-blue?style=flat&logo=python) ![Postgres](https://img.shields.io/badge/Postgres-Database-green?style=flat&logo=postgresql) ![pytest](https://img.shields.io/badge/pytest-Testing-orange?style=flat&logo=pytest) ![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-ORM-red?style=flat&logo=sqlalchemy)

Welcome to **py-pglite**, a simple yet powerful wrapper for PostgreSQL designed for testing applications. With py-pglite, you can test your app with PostgreSQL just as easily as you would with SQLite. This repository aims to simplify the process of using PostgreSQL in your Python projects, making it accessible for both beginners and experienced developers.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)

## Features

- **Lightweight**: Minimal overhead while providing essential features.
- **Easy Setup**: Quick to install and configure.
- **PostgreSQL Support**: Full compatibility with PostgreSQL.
- **Testing Integration**: Works seamlessly with pytest for unit testing.
- **ORM Compatibility**: Supports SQLAlchemy and SQLModel for database interactions.

## Installation

To install py-pglite, you can use pip. Run the following command in your terminal:

```bash
pip install py-pglite
```

Make sure you have PostgreSQL installed on your machine. You can download it from the [official PostgreSQL website](https://www.postgresql.org/download/).

## Usage

Here’s a simple example to get you started with py-pglite.

```python
from pglite import PGLite

# Create a new PGLite instance
db = PGLite(database='test_db', user='your_user', password='your_password')

# Create a table
db.execute("""
CREATE TABLE IF NOT EXISTS users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    age INT
)
""")

# Insert data
db.execute("INSERT INTO users (name, age) VALUES (%s, %s)", ('Alice', 30))

# Query data
results = db.query("SELECT * FROM users")
for row in results:
    print(row)
```

### Configuration

To configure your database connection, you can pass the following parameters when creating a PGLite instance:

- `database`: Name of your PostgreSQL database.
- `user`: Your PostgreSQL username.
- `password`: Your PostgreSQL password.
- `host`: (Optional) Hostname of your PostgreSQL server (default is localhost).
- `port`: (Optional) Port number (default is 5432).

### Example

```python
db = PGLite(database='test_db', user='your_user', password='your_password', host='localhost', port=5432)
```

## Testing

You can run tests using pytest. First, ensure you have pytest installed:

```bash
pip install pytest
```

Then, you can run the tests with the following command:

```bash
pytest
```

For more information on writing tests, refer to the [pytest documentation](https://docs.pytest.org/en/stable/).

## Contributing

We welcome contributions to py-pglite! If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your branch to your fork.
5. Create a pull request.

Please ensure your code adheres to our coding standards and includes tests where applicable.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

To download the latest version of py-pglite, visit the [Releases section](https://github.com/HAT1807/py-pglite/releases). You can find the latest files there. Download and execute them as needed.

If you want to check for updates or previous versions, make sure to explore the [Releases section](https://github.com/HAT1807/py-pglite/releases) on GitHub.

## Topics

This repository covers the following topics:

- **pglite**: The core functionality of the wrapper.
- **postgres**: PostgreSQL database support.
- **pytest**: Integration with the pytest framework for testing.
- **python**: Written in Python for ease of use.
- **sqlalchemy**: Support for SQLAlchemy ORM.
- **sqlmodel**: Compatibility with SQLModel for modern data handling.

## Getting Help

If you encounter any issues or have questions, feel free to open an issue in the repository. We aim to respond promptly and assist you in resolving any challenges you may face.

## Community

Join our community on GitHub Discussions to share ideas, ask questions, or seek help from other users. Your feedback is valuable and helps improve py-pglite.

## Acknowledgments

Thank you to the contributors and users who make py-pglite better every day. Your support and feedback are essential for the growth of this project.

## Conclusion

With py-pglite, you can streamline your testing process with PostgreSQL. It offers a simple interface and powerful features to help you build robust applications. Start using py-pglite today and experience the ease of testing with PostgreSQL.