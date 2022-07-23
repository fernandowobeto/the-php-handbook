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

