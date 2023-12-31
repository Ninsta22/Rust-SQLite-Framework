[![Build binary release](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/release.yml/badge.svg)](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/release.yml)
[![Lints](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/lint.yml/badge.svg)](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/lint.yml)
[![Format](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/rustfmt.yml/badge.svg)](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/rustfmt.yml)
[![Tests](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/tests.yml/badge.svg)](https://github.com/nogibjj/kb545-rust-python-compare/actions/workflows/tests.yml)

# Rust SQLite CLI with Binary

The goal of this project was to create a Rust repository that is able to create an SQLite databse, populate it with any csv document (I elected to work with the standard ```iris.csv``` dataset), and execute any user inputted query. This project is a CLI to maximize ease of use for a user, and allow them to query whatever they want. There is constant error handling and logging implemented for any situation that may arise, and the entire project is wrapped in a Rust Binary file. This project was created while adhering to DevOps principles, and is fully tested, linted, formatted, and built. A deeper explanation of the project, and how to run it, is explained below.

### Project Explanation
The goal of this project was to create a Rust CLI with SQLite. The Rust CLI was used with ```clap```, to get the user command-line input. The input will be a valid SQL query. Once recieved, the code will utilize ```rusqlite``` and create a SQLite database object. Then, this database will have a table created, with the values populated from a csv documnet. Utilizing the ```csv``` crate, the dataset will be fully read in and used to fully populate the table. At this stage, the script will then execute the user inputted query, and print back on the command line the result. There is logging to detect if populating the data, and if the SQL query, output an error. This is done by working alongside ```std::error```. The full list of dependencies used, and their respective versions is found in the file ```Cargo.toml```

There is testing implemented to determine if the database was properly created, as well as a SQL query execution is valid or not. The code is also properly linted (with Clippy) and formatted.

* To test the code, run ```make test```
* To lint the code, run ```make lint```
* To format the code, run ```make format```
* To run the code, run ```cargo run -- --query "YOUR QUERY HERE"``` (This will install all of the required dependencies before executing)
* To create the Rust Binary file, run ```make release```

### CRUD Opeartions
The following below are screenshots that demonstrates that the code supports C.R.U.D operations (Create, Read, Update, Delete). All of them are SQL queries that were successfully executed.

* **Create**

![image](https://github.com/Ninsta22/Rust-SQLite-Framework/assets/55768636/fc2caea6-34a4-4a21-aafd-ce3e9c098965)

* **Read**

![image](https://github.com/Ninsta22/Rust-SQLite-Framework/assets/55768636/d63c6ed0-6c3f-4152-90db-f73649b32c93)

* **Update**

![Alt text](image-1.png)

* **Delete**

![Alt text](image-2.png)



### Rust Binary

In the parent directory, there is the Rust Binary file. This file can be used to run the entire Rust script. If one were to work with this project locally, and recreate it, you can easily generate a binary file from running ```make release``` in the command line. You can identify that the Rust Binary will properly be generated from the GitHub Actions badge attached to this README.

### Demo Video

https://www.youtube.com/watch?v=tdjZms4La1g



