# PHP
`PHP: Hypertext Preprocessor (PHP)` is a general-purpose, server-side scripting language. The default file extension for `PHP` files is `.php` that run on a server.

+ [Hello World](#hello-world)
+ [Comments](#comments)
+ [Superglobal](#superglobal)

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
