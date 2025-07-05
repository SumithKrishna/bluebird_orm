# Bluebird ORM: A Lightweight and Fast ORM for Python

![Bluebird ORM](https://img.shields.io/badge/Bluebird%20ORM-Python%20ORM-blue)

[![Releases](https://img.shields.io/badge/Releases-Check%20Here-brightgreen)](https://github.com/SumithKrishna/bluebird_orm/releases)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Supported Databases](#supported-databases)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Bluebird ORM is a simple and lightweight Object-Relational Mapping (ORM) library for Python. It provides an easy way to interact with databases while keeping your code clean and efficient. Whether you are building a small application or a larger system, Bluebird ORM helps you manage your database interactions smoothly.

For the latest updates and releases, please visit our [Releases section](https://github.com/SumithKrishna/bluebird_orm/releases).

---

## Features

- **Blazing Fast**: Optimized for speed, Bluebird ORM ensures quick database interactions.
- **Lightweight**: Minimal footprint, making it easy to integrate into any project.
- **Simple API**: Intuitive interface that reduces the learning curve.
- **Supports Multiple Databases**: Works seamlessly with PostgreSQL, SQLite, and more.
- **Easy Setup**: Get started quickly with straightforward installation.

---

## Installation

To install Bluebird ORM, you can use pip. Run the following command in your terminal:

```bash
pip install bluebird_orm
```

For the latest version, check the [Releases section](https://github.com/SumithKrishna/bluebird_orm/releases).

---

## Getting Started

To begin using Bluebird ORM, you need to set up a connection to your database. Here’s how you can do it:

### Basic Setup

1. **Import the Library**:

```python
from bluebird_orm import Database
```

2. **Create a Database Connection**:

```python
db = Database('sqlite:///my_database.db')  # For SQLite
# or
db = Database('postgresql://user:password@localhost/my_database')  # For PostgreSQL
```

3. **Define Your Models**:

```python
class User(db.Model):
    __tablename__ = 'users'
    
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String)
    email = db.Column(db.String)
```

4. **Create the Tables**:

```python
db.create_all()
```

---

## Usage

### Basic CRUD Operations

#### Create

```python
new_user = User(name='John Doe', email='john@example.com')
db.session.add(new_user)
db.session.commit()
```

#### Read

```python
users = db.session.query(User).all()
for user in users:
    print(user.name, user.email)
```

#### Update

```python
user = db.session.query(User).filter_by(name='John Doe').first()
user.email = 'john.doe@example.com'
db.session.commit()
```

#### Delete

```python
user = db.session.query(User).filter_by(name='John Doe').first()
db.session.delete(user)
db.session.commit()
```

---

## Supported Databases

Bluebird ORM supports the following databases:

- **PostgreSQL**: Use with the `psycopg2` driver.
- **SQLite**: Native support for SQLite databases.
- **Other Databases**: Easily extendable to support more databases as needed.

---

## Contributing

We welcome contributions to Bluebird ORM. Here’s how you can help:

1. **Fork the Repository**: Create your own copy of the repository.
2. **Create a Branch**: Make a new branch for your feature or bug fix.
3. **Make Changes**: Implement your changes in the code.
4. **Submit a Pull Request**: Share your changes with us for review.

---

## License

Bluebird ORM is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

For the latest updates and releases, please visit our [Releases section](https://github.com/SumithKrishna/bluebird_orm/releases).