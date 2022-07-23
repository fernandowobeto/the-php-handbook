# THE PHP HANDBOOK

Esta é uma tradução do artigo original de Flavio Copes em https://www.freecodecamp.org/news/the-php-handbook

PHP is an incredibly popular programming language.

Statistics say it’s used by 80% of all websites. It’s the language that powers WordPress, the widely used content management system for websites.

And it also powers a lot of different frameworks that make Web Development easier, like Laravel. Speaking of Laravel, it may be one of the most compelling reasons to learn PHP these days.

Why Learn PHP?
PHP is quite a polarizing language. Some people love it, and some people hate it. If we move a step above the emotions and look at the language as a tool, PHP has a lot to offer.

Sure it’s not perfect. But let me tell you – no language is.

In this handbook, I’m going to help you learn PHP.

This book is a perfect introduction if you’re new to the language. It’s also perfect if you’ve done “some PHP” in the past and you want to get back to it.

I’ll explain modern PHP, version 8+.

PHP has evolved a lot in the last few years. So if the last time you tried it was PHP 5 or even PHP 4, you’ll be surprised at all the good things that PHP now offers.

Let’s go!

Here's what we'll cover in this handbook:

1. Introduction to PHP
2. What Kind of Language is PHP?
3. How to Setup PHP
4. How to Code Your First PHP Program
5. PHP Language Basics
6. How to Work with Strings in PHP
7. How to Use Built-in Functions for Numbers in PHP
8. How Arrays Work in PHP
9. How Conditionals Work in PHP
10. How Loops Work in PHP
11. How Functions Work in PHP
12. How to Loop Through Arrays with map(), filter(), and reduce() in PHP
13. Object Oriented Programming in PHP
14. How to Include Other PHP Files
15. Useful Constants, Functions and Variables for Filesystem in PHP
16. How to Handle Errors in PHP
17. How to Handle Exceptions in PHP
18. How to Work with Dates in PHP
19. How to Use Constants and Enums in PHP
20. How to Use PHP as a Web App Development Platform
21. How to Use Composer and Packagist
22. How to Deploy a PHP Application
23. Conclusion

## Introduction to PHP
PHP is a programming language that many devs use to create Web Applications, among other things.

As a language, it had a humble beginning. It was first created in 1994 by Rasmus Lerdorf to build his personal website. He didn’t know at the time it would eventually become one of the most popular programming languages in the world. It became popular later on, in 1997/8, and exploded in the 2000s when PHP 4 landed.

You can use PHP to add a little interactivity to an HTML page.

Or you can use it as a Web Application engine that creates HTML pages dynamically and sends them to the browser.

It can scale to millions of page views.

Did you know Facebook is powered by PHP? Ever heard of Wikipedia? Slack? Etsy?

## What Kind of Language is PHP?
Let’s get into some technical jargon.

Programming languages are divided into groups depending on their characteristics. For example interpreted/compiled, strongly/loosely typed, dynamically/statically typed.

PHP is often called a “scripting language” and it’s an interpreted language. If you’ve used compiled languages like C or Go or Swift, the main difference is that you don’t need to compile a PHP program before you run it.

Those languages are compiled and the compiler generates an executable program that you then run. It’s a 2-steps process.

The PHP interpreter is responsible for interpreting the instructions written in a PHP program when it’s executed. It’s just one step. You tell the interpreter to run the program. It's a completely different workflow.

PHP is a dynamically typed language. The types of variables are checked at runtime, rather than before the code is executed as happens for statically typed languages. (These also happen to be compiled – the two characteristics often go hand in hand.)

PHP is also loosely (weakly) typed. Compared to strongly typed languages like Swift, Go, C or Java, you don’t need to declare the types of your variables.

Being interpreted and loosely/dynamically typed will make bugs harder to find before they happen at runtime.

In compiled languages, you can often catch errors at compile time, something that does not happen in interpreted languages.

But on the other hand, an interpreted language has more flexibility.

Fun fact: PHP is written internally in C, a compiled and statically typed language.

In its nature, PHP is similar to JavaScript, another dynamically typed, loosely typed, and interpreted language.

PHP supports object-oriented programming, and also functional programming. You can use it as you prefer.

## How to Setup PHP
There are many ways to install PHP on your local machine.

The most convenient way I’ve found to install PHP locally is to use MAMP.

MAMP is a tool that’s freely available for all the Operating Systems – Mac, Windows and Linux. It is a package that gives you all the tools you need to get up and running.

PHP is run by a HTTP Server, which is responsible for responding to HTTP requests, the ones made by the browser. So you access a URL with your browser, Chrome or Firefox or Safari, and the HTTP server responds with some HTML content.

The server is typically Apache or NGINX.

Then to do anything non-trivial you’ll need a database, like MySQL.

MAMP is a package that provides all of that, and more, and gives you a nice interface to start/stop everything at once.

Of course, you can set up each piece on its own if you like, and many tutorials explain how to do that. But I like simple and practical tools, and MAMP is one of those.

You can follow this handbook with any kind of PHP installation method, not just MAMP.

That said, if you don’t have PHP installed yet and you want to use MAMP, go to https://www.mamp.info and install it.

The process will depend on your operating system, but once you’re done with the installation, you will have a “MAMP” application installed.

Start that, and you will see a window similar to this:

![alt text](images/how_to_setup.jpg "How to setup PHP")

Make sure the PHP version selected is the latest available.

At the time of writing MAMP lets you pick 8.0.8.

NOTE: I noticed MAMP has a version that’s a bit behind, not the latest. You can install a more recent version of PHP by enabling the MAMP PRO Demo, then install the latest release from the MAMP PRO settings (in my case it was 8.1.0). Then close it and reopen MAMP (non-pro version). MAMP PRO has more features so you might want to use it, but it’s not necessary to follow this handbook.

Press the Start button at the top right. This will start the Apache HTTP server, with PHP enabled, and the MySQL database.

Go to the URL http://localhost:8888 and you will see a page similar to this:
![alt text](images/how_to_setup_ready.jpg "How to setup PHP")

We’re ready to write some PHP!

Open the folder listed as “Document root”. If you're using MAMP on a Mac it’s by default /Applications/MAMP/htdocs.

On Windows it’s C:\MAMP\htdocs.

Yours might be different depending on your configuration. Using MAMP you can find it in the user interface of the application.

In there, you will find a file named index.php.

That is responsible for printing the page shown above.
![alt text](images/how_to_setup_index_folder.jpg "How to setup PHP")

## How to Code Your First PHP Program
When learning a new programming language we have this tradition of creating a “Hello, World!” application. Something that prints those strings.

Make sure MAMP is running, and open the htdocs folder as explained above.

Open the index.php file in a code editor.

I recommend using VS Code, as it’s a very simple and powerful code editor. You can check out https://flaviocopes.com/vscode/ for an introduction.
![alt text](images/first_code_vscode.jpg "First Program VSCODE")

This is the code that generates the “Welcome to MAMP” page you saw in the browser.

Delete everything and replace it with:
```php
<?php
echo 'Hello World';
?>
```

Save, refresh the page on http://localhost:8888, you should see this:
![alt text](images/first_code_hello_world.jpg "First Program Hello World")

Great! That was your first PHP program.

Let’s explain what is happening here.

We have the Apache HTTP server listening on port 8888 on localhost, your computer.

When we access http://localhost:8888 with the browser, we’re making an HTTP request, asking for the content of the route /, the base URL.

Apache, by default, is configured to serve that route serving the index.html file included in the htdocs folder. That file does not exist – but as we have configured Apache to work with PHP, it will then search for an index.php file.

This file exists, and PHP code is executed server-side before Apache sends the page back to the browser.

In the PHP file, we have a <?php opening, which says “here starts some PHP code”.

We have an ending ?> that closes the PHP code snippet, and inside it, we use the echo instruction to print the string enclosed into quotes into the HTML.

A semicolon is required at the end of every statement.

We have this opening/closing structure because we can embed PHP inside HTML. PHP is a scripting language, and its goal is to be able to “decorate” an HTML page with dynamic data.

Note that with modern PHP, we generally avoid mixing PHP into the HTML. Instead, we use PHP as a “framework to generate the HTML” – for example using tools like Laravel. But we'll discuss plain PHP in this book, so it makes sense to start from the basics.

For example, something like this will give you the same result in the browser:
```php
Hello
<?php
echo 'World';
?>
```

To the final user, who looks at the browser and has no idea of the code behind the scenes, there’s no difference at all.

The page is technically an HTML page, even though it does not contain HTML tags but just a Hello World string. But the browser can figure out how to display that in the window.

## PHP Language Basics
After the first “Hello World”, it’s time to dive into the language features with more details.

### How Variables Work in PHP
Variables in PHP start with the dollar sign $, followed by an identifier, which is a set of alphanumeric chars and the underscore _ char.

You can assign a variable any type of value, like strings (defined using single or double quotes):
```php
$name = 'Flavio';

$name = "Flavio";
```

Or numbers:
```php
$age = 20;
```

or any other type that PHP allows, as we’ll later see.

Once a variable is assigned a value, for example a string, we can reassign it a different type of value, like a number:
```php
$name = 3;
```

PHP won’t complain that now the type is different.

Variable names are case-sensitive. $name is different from $Name.

It’s not a hard rule, but generally variable names are written in camelCase format, like this: $brandOfCar or $ageOfDog. We keep the first letter lowercase, and the letters of the subsequent words uppercase.

## How to Write Comments in PHP
A very important part of any programming language is how you write comments.

You write single-line comments in PHP in this way:
```php
// single line comment
```

Multi-line comments are defined in this way:
```php
/*

this is a comment

*/

//or

/*
 *
 * this is a comment
 *
 */

//or to comment out a portion of code inside a line:

/* this is a comment */
```

### What are Types in PHP?
I mentioned strings and numbers.

PHP has the following types:

* `bool` boolean values (true/false)
* `int` integer numbers (no decimals)
* `float` floating-point numbers (decimals)
* `string` strings
* `array` arrays
* `object` objects
* `null` a value that means “no value assigned”

and a few other more advanced ones.

## How to Print the Value of a Variable in PHP
We can use the `var_dump()` built-in function to get the value of a variable:
```php
$name = 'Flavio';

var_dump($name);
```

The `var_dump($name)` instruction will print `string(6) "Flavio"` to the page, which tells us the variable is a string of 6 characters.

If we used this code:
```php
$age = 20;

var_dump($age);
```

we’d have `int(20)` back, saying the value is 20 and it’s an integer.

`var_dump()` is one of the essential tools in your PHP debugging tool belt.

## How Operators Work in PHP
Once you have a few variables you can make operations with them:
```php
$base = 20;
$height = 10;

$area = $base * $height;
```

The `*`  I used to multiply $base by $height is the multiplication operator.

We have quite a few operators – so let’s do a quick roundup of the main ones.

To start with, here are the arithmetic operators: `+`, `-`, `*`, `/` (division), `%` (remainder) and `**` (exponential).

We have the assignment operator `=`, which we already used to assign a value to a variable.

Next up we have comparison operators, like `<`, `>`, `<=`, `>=`. Those work like they do in math.
```php
2 < 1; //false
1 <= 1; // true
1 <= 2; // true
```

`==` returns true if the two operands are equal.

`===` returns true if the two operands are identical.

What’s the difference?

You’ll find it with experience, but for example:
```php
1 == '1'; //true
1 === '1'; //false
```

We also have `!=` to detect if operands are not equal:
```php
1 != 1; //false
1 != '1'; //false
1 != 2; //true

//hint: <> works in the same way as !=, 1 <> 1
```

and `!==` to detect if operands are not identical:
```php
1 !== 1; //false
1 !== '1'; //true
```

Logical operators work with boolean values:
```php
// Logical AND with && or "and"

true && true; //true
true && false; //false
false && true; //false
false && false; //false

true and true; //true
true and false; //false
false and true; //false
false and false; //false

// Logical OR with || or "or"

true || true; // true
true || false //true
false || true //true
false || false //false

true or true; // true
true or false //true
false or true //true
false or false //false

// Logical XOR (one of the two is true, but not both)

true xor true; // false
true xor false //true
false xor true //true
false xor false //false
```

We also have the not operator:
```php
$test = true

!$test //false
```

I used the boolean values true and false here, but in practice you’ll use expressions that evaluate to either true or false, for example:
```php
1 > 2 || 2 > 1; //true

1 !== 2 && 2 > 2; //false
```

All of the operators listed above are binary, meaning they involve 2 operands.

PHP also has 2 unary operators: `++` and `--`:
```php
$age = 20;
$age++;
//age is now 21

$age--;
//age is now 20
```

## How to Work with Strings in PHP
I introduced the use of strings before when we talked about variables and we defined a string using this notation:
```php
$name = 'Flavio'; //string defined with single quotes

$name = "Flavio"; //string defined with double quotes
```

The big difference between using single and double quotes is that with double quotes we can expand variables in this way:
```php
$test = 'an example';

$example = "This is $test"; //This is an example
```

and with double quotes we can use escape characters (think new lines `\n` or tabs `\t`):
```php
$example = "This is a line\nThis is a line";

/*
output is:

This is a line
This is a line
*/
```

PHP offers you a very comprehensive functions in its standard library (the library of functionalities that the language offers by default).

First, we can concatenate two strings using the `.` operator:
```php
$firstName = 'Flavio';
$lastName = 'Copes';

$fullName = $firstName . ' ' . $lastName;
```

We can check the length of a string using the `strlen()` function:
```php
$name = 'Flavio';
strlen($name); //6
```

This is the first time we've used a function.

A function is composed of an identifier (`strlen` in this case) followed by parentheses. Inside those parentheses, we pass one or more arguments to the function. In this case, we have one argument.

The function does something and when it’s done it can return a value. In this case, it returns the number `6`. If there’s no value returned, the function returns `null`.

We’ll see how to define our own functions later.

We can get a portion of a string using `substr()`:
```php
$name = 'Flavio';
substr($name, 3); //"vio" - start at position 3, get all the rest
substr($name, 2, 2); //"av" - start at position 2, get 2 items
```

We can replace a portion of a string using str_replace():
```php
$name = 'Flavio';
str_replace('avio', 'ower', $name); //"Flower"
```

Of course we can assign the result to a new variable:
```php
$name = 'Flavio';
$itemObserved = str_replace('avio', 'ower', $name); //"Flower"
```

Here is a brief non-comprehensive list just to show you the possibilities:
* `trim()` strips white space at the beginning and end of a string
* `strtoupper()` makes a string uppercase
* `strtolower()` makes a string lowercase
* `ucfirst()` makes the first character uppercase
* `strpos()` finds the firsts occurrence of a substring in the string
* `explode()` to split a string into an array
* `implode()` to join array elements in a string

You can find a full list [here](https://www.php.net/manual/en/book.strings.php).

## How to Use Built-in Functions for Numbers in PHP
I previously listed the few functions we commonly use for strings.

Let’s make a list of the functions we use with numbers:
* `round()` to round a decimal number, up/down depending if the value is > 0.5 or smaller
* `ceil()` to round a a decimal number up
* `floor()` to round a decimal number down
* `rand()` generates a random integer
* `min()` finds the lowest number in the numbers passed as arguments
* `max()` finds the highest number in the numbers passed as arguments
* `is_nan()` returns true if the number is not a number

There are a ton of different functions for all sorts of math operations like sine, cosine, tangents, logarithms, and so on. You can find a full list [here](https://www.php.net/manual/en/book.math.php).

## How Arrays Work in PHP
Arrays are lists of values grouped under a common name.

You can define an empty array in two different ways:
```php
$list = [];

$list = array();
```

An array can be initialized with values:
```php
$list = [1, 2];

$list = array(1, 2);
```

Arrays can hold values of any type:
```php
$list = [1, 'test'];
```

Even other arrays:
```php
$list = [1, [2, 'test']];
```

You can access the element in an array using this notation:
```php
$list = ['a', 'b'];
$list[0]; //'a' --the index starts at 0
$list[1]; //'b'
```

Once an array is created, you can append values to it in this way:
```php
$list = ['a', 'b'];
$list[] = 'c';

/*
$list == [
  "a",
  "b",
  "c",
]
*/
```

You can use `array_unshift()` to add the item at the beginning of the array instead:
```php
$list = ['b', 'c'];
array_unshift($list, 'a');

/*
$list == [
  "a",
  "b",
  "c",
]
*/
```

Count how many items are in an array using the built-in `count()` function:
```php
$list = ['a', 'b'];

count($list); //2
```

Check if an array contains an item using the `in_array()` built-in function:
```php
$list = ['a', 'b'];

in_array('b', $list); //true
```

If in addition to confirming existence, you need the index, use `array_search()`:
```php
$list = ['a', 'b'];

array_search('b', $list) //1
```

## Useful Functions for Arrays in PHP
As with strings and numbers, PHP provides lots of very useful functions for arrays. We’ve seen `count()`, `in_array()`, `array_search()` – let’s see some more:

* `is_array()` to check if a variable is an array
* `array_unique()` to remove duplicate values from an array
* `array_search()` to search a value in the array and return the key
* `array_reverse()` to reverse an array
* `array_reduce()` to reduce an array to a single value using a callback function
* `array_map()` to apply a callback function to each item in the array. 
Typically used to create a new array by modifying the values of an existing array, without altering it.
* `array_filter()` to filter an array to a single value using a callback function
* `max()` to get the maximum value contained in the array
* `min()` to get the minimum value contained in the array
* `array_rand()` to get a random item from the array
* `array_count_values()` to count all the values in the array
* `implode()` to turn an array into a string
* `array_pop()` to remove the last item of the array and return its value
* `array_shift()` same as `array_pop()` but removes the first item instead of the last
* `sort()` to sort an array
* `rsort()` to sort an array in reverse order
* `array_walk()` similarly to `array_map()` does something for every item in the array, but in addition it can change values in the existing array

## How to Use Associative Arrays in PHP