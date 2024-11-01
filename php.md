# PHP
`PHP: Hypertext Preprocessor (PHP)` is a general-purpose, server-side scripting language. The default file extension for `PHP` files is `.php` that run on a server.

+ [Hello World](#hello-world)
+ [Comments](#comments)
+ [Superglobal](#superglobal)
+ [Functions](#functions)
  + [Arguments](#arguments)
+ [Database Connection](#database-connection)

## Hello World
A simple `PHP` script may look like the following example (below). This is written in a file named `hello.php` and will print `Hello World` onto a webpage. The closing `?>` at the end of the script is optional if the code only contains `PHP` code.

```php
<?php
  echo "Hello World";
?>
```

## Comments
Code comments are added to describe the code in a human-readable format. `PHP` uses `C`, `C++` and Unix shell-style (`Perl`) style comments.

```php
// This is a one-line comment using C++ style

# This is a one-line comment using shell-style

/* This is a multi-line comment
   yet another line comment */
```

## Superglobal
In `PHP`, a `superglobal` is a special reserved PHP `variable`. An example of this is `S_SERVER`, which is a superglobal variable that contains web server information. A `variable` in `PHP` always begins with a `dollar sign ($)`. We can use the `S_SERVER` variable to return the `HTTP User Agent` being used. An example of the value returned would be: `Mozilla/5.0 (Linux) Firefox/112.0`.

```php
<?php
  echo $_SERVER["HTTP_USER_AGENT"];
?>
```

```php
<?php
  if (str_contains($_SERVER["HTTP_USER_AGENT"], "Firefox")) {
    echo "You are using Firefox.";
  }
?>
```

## Functions
+ A `function` is a block of statements that can be used repeatedly in a program.
+ A `function` will not execute automatically when a page loads.
+ The `function` will be executed by a call to the `function`.

 ```php
<?php
  function foo()
  {
    echo "This is a function.";
  }

  // Call the function to execute the code
  foo();
?>
```

### Arguments

Data can be passed into functions using `arguments`. 

 ```php
<?php
  function foo($argument)
  {
    echo "This is a function. The argument is: $argument";
  }

  // Call the function to execute the code
  foo("Hello World");
?>
```

An `argument` can also have a `default value`.

 ```php
<?php
  function foo($argument = "Hello World")
  {
    echo "This is a function. The argument is: $argument";
  }

  // Call the function to execute the code
  foo();          // This will return: This is a function. The argument is: Hello World
  foo("Hello");   // This will return: This is a function. The argument is: Hello
?>
```

## Database Connection
A connection to a database, such as `MySQL`, can be made using `PDO (PHP Data Objects)`. `PDO` requires a valid database to connect to or an exception will be thrown. 

```php
<?php
  // Database connection variables
  $hostname = "localhost";
  $username = "username";
  $password = "password";
  $database = "databaseName";
  
  try {
    // Create a PDO instance with MySQL DSN (Data Source Name)
    $conn = new PDO("mysql:host=$hostname;dbname=$database", $username, $password);
    // Set the PDO error mode to exception for better error handling
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Connected to the database.";
  } catch(PDOException $e) {
    // Display the exact error during development, better to remove this and log this in production
    echo "Connection failed: " . $e->getMessage();
  }
?>
```
