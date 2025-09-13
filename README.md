# alu-AirBnB

An AirBnB clone.

---

## Description

**alu-AirBnB** is a project that recreates the core features of the AirBnB web application. This is the first step towards building a complete web application, integrating database storage, a back-end API, and front-end interfacing. In this stage, we focus on a custom command-line interface for data management and the base classes for data storage.

The command interpreter (console) allows you to create, show, update, and destroy objects, and persists them using JSON serialization.

---

## Usage

### Setup

First, clone this repository:

```bash
git clone https://github.com/<your-username>/alu-AirBnB.git
cd alu-AirBnB
```

### Running the Console

To start the console, run:

```bash
./console.py
```

You should see the following prompt:

```
(hbnb)
```

This prompt indicates that you are in the "HBnB" console, ready to interact with your data models.

---

## Commands

| Command    | Description                                                                   |
|------------|-------------------------------------------------------------------------------|
| `create`   | Creates an instance based on the given class                                  |
| `show`     | Shows an object based on class and UUID                                       |
| `destroy`  | Destroys an object based on class and UUID                                    |
| `all`      | Shows all objects, or all objects of a given class                            |
| `update`   | Updates attributes of an object based on class name and UUID                  |
| `quit`     | Exits the program (EOF also exits)                                            |

### Alternative Syntax

You can also use dot notation for commands:

```
<class_name>.<command>([<id>[, <attr_name>, <attr_value>]|[kwargs]])
```

Supported commands with advanced syntax:

- all
- count
- show
- destroy
- update

---

## Examples

### Primary Command Syntax

#### Example 0: Create an object

```bash
(hbnb) create BaseModel
3aa5babc-efb6-4041-bfe9-3cc9727588f8
```

#### Example 1: Show an object

```bash
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
[BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', ...}
```

#### Example 2: Destroy an object

```bash
(hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
** no instance found **
```

#### Example 3: Update an object

```bash
(hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
(hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
[BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'first_name': 'person', ...}
```

---

### Alternative Syntax

#### Example 0: Show all User objects

```bash
(hbnb) User.all()
["[User] (...)", "[User] (...)"]
```

#### Example 1: Destroy a User

```bash
(hbnb) User.destroy("user-uuid")
(hbnb) User.all()
[]
```

#### Example 2: Update User (by attribute)

```bash
(hbnb) User.update("user-uuid", name"Jayden Mugabo")
```

#### Example 3: Update User (by dictionary)

```bash
(hbnb) User.update("user-uuid", {'name': 'Sonia Zuba', 'age': 18})
```

---

## Project Structure

```
.
├── README.md
├── console.py
├── models/
│   ├── __init__.py
│   ├── base_model.py
│   ├── user.py
│   ├── state.py
│   ├── city.py
│   ├── place.py
│   ├── amenity.py
│   ├── review.py
│   └── engine/
│       ├── __init__.py
│       └── file_storage.py
└── tests/
    ├── test_console.py
    └── test_models/
        ├── test_base_model.py
        └── ...
```

---

## Requirements

- Python 3.8.5 (Ubuntu 20.04 LTS)
- PEP8 compliant code (`pycodestyle 2.7.*`)
- All modules, classes, and methods are documented
- Scripts are executable (`chmod +x filename`)
- Unit tests in the `tests/` directory

### Running Tests

To run all tests:

```bash
python3 -m unittest discover tests
```

---

## Authors

- Elyse ISHIMWE <e.ishimwe3@alustudent.com>
- Frank NKURUNZIZA <f.nkurunziz2@alustudent.com>

---
