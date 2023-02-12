# AirBnB Clone

![Logo](media/hbnb.png "hbnb logo")

## Table of Contents

<!-- TOC -->

* [About](#about)
* [General concepts involved](#general-concepts-applied)
* [Project objects description](#project-objects-description)
* [Implementation](#implementation)
* [Supported Commands](#supported-commands)
* [Execution](#execution)

<!-- TOC -->

## About

The ALX-Holberton B&B sums up the implementation of my four months of studies
at the ALX-Holberton School—the fullstack software engineering program.
The goal of the project is to deploy on your server a simple copy of the [Airbnb Website](https://www.airbnb.com/).
The final product will have these features::

* A command interpreter to manipulate data without a visual interface, like a shell (for development and debugging)
* A website (front-end) with static and dynamic functionalities
* A comprehensive database to manage the backend functionalities
* An API that provides a communication interface between the front and backend of the system.

## General concepts applied

* How to create a Python package
* How to create a command interpreter in Python using the cmd module
* What is Unit testing and how to implement it in a large project
* How to serialize and deserialize a Class
* How to write and read a JSON file
* How to manage datetime
* What is a UUID
* What is *args and how to use it
* What is **kwargs and how to use it
* How to handle named arguments in a function

## Project objects description

* ```models``` directory contains all classes used for the entire project.
  A class, called “model” in an OOP project is the representation of an object/instance.
* ```tests``` directory contains all unit tests.
* ```console.py``` file is the entry point of the command interpreter.
* ```models/base_model.py``` file is the base class of all our models. It contains common elements:
  * attributes: ```id```, ```created_at``` and ```updated_at```
  * methods: ```save()``` and ```to_json()```
* ```models/engine``` directory contains all storage classes (using the same prototype), such as: ```file_storage.py```.

## Implementation

The goal is to manipulate a powerful storage system to give an abstraction
between objects and how they are stored and persisted.
This was achieved by:

* putting in place a parent class (called ```BaseModel```) to take care of the initialization,
  serialization and deserialization of my future instances
* creating a simple flow of serialization/deserialization: Instance <-> Dictionary <-> JSON string <-> file
* creating all classes used for AirBnB (```User, State, City, Place…```) that inherit from ```BaseModel```
* creating the first abstracted storage engine of the project: File storage.
* creating all unittests to validate all our classes and storage engine
* Creating a data model
* Managing (create, update, destroy, etc) objects via a console/command interpreter
* Storing and persist objects to files (JSON files)
  S

## Supported Commands

|                            Commands                            | Description                                                                                                              |
|:--------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------------------|
|                           ```quit```                           | Quits the console                                                                                                        |
|                          ```Ctrl+D```                          | Quits the console                                                                                                        |
|               ```help``` or ```help <command>```               | Displays all commands or Displays instructions for a specific command                                                    |
|                      ```create <class>```                      | Creates an object of type , saves it to a JSON file, and prints the objects ID                                           |
|                    ```show <class> <ID>```                     | Shows string representation of an object                                                                                 |
|                   ```destroy <class> <ID>```                   | Deletes an objects                                                                                                       |
|                    ```all or all <class>```                    | Prints all string representations of all objects or Prints all string representations of all objects of a specific class |
| ```update <class> <id> <attribute name> "<attribute value>"``` | Updates an object with a certain attribute (new or existing)                                                             |
|                      ```<class>.all()```                       | Same as all ```<class>```                                                                                                |
|                     ```<class>.count()```                      | Retrieves the number of objects of a certain class                                                                       |
|                    ```<class>.show(<ID>)```                    | Same as show ```<class> <ID>```                                                                                          |
|                  ```<class>.destroy(<ID>)```                   | Same as destroy ```<class> <ID>```                                                                                       |
| ```<class>.update(<ID>, <attribute name>, <attribute value>``` | Same as update ```<class> <ID> <attribute name> <attribute value>```                                                     |
|    ```<class>.update(<ID>, <dictionary representation>)```     | Updates an objects based on a dictionary representation of attribute names and values                                    |

## Execution

The shell should work like this in `interactive mode`:

```console
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
(hbnb) 
(hbnb) quit
$
But also in non-interactive mode: (like the Shell project in C)

$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```
