# What is singleton design pattern with example in php?
The singleton design pattern is a type of software design pattern that restricts the instantiation of a class to one object. This is useful when exactly one object is needed to coordinate actions across the system.
For example, a logging class could be implemented using the singleton design pattern. This class would provide a single point of access for logging information.
Example in PHP:
```
<?php

class Logger
{
    private static $instance;

    private function __construct()
    {
        // Constructor is private to prevent instantiation
    }

    public static function getInstance()
    {
        if (!self::$instance) {
            self::$instance = new Logger();
        }

        return self::$instance;
    }
}

// Usage
$logger = Logger::getInstance();
```
