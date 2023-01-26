# What is Dependency Inversion Principle in php with example?
Dependency Inversion Principle is a software design principle that states:

“High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.”

In other words, a software design should depend on abstractions (interfaces and abstract classes) instead of concrete implementations. 

Example:

Let’s say we have a class called DatabaseConnection that is responsible for connecting to a database.
```
//Low-level module
class DatabaseConnection
{
   public function connect()
   {
       // connect to the database
   }
}

//High-level module
class UserRepository 
{
    private $db;

    public function __construct(DatabaseConnection $db)
    {
        $this->db = $db;
    }
}
```
In this example, the UserRepository class depends on the DatabaseConnection class, which is a low-level module. This is not ideal because if we want to change the database system, we would have to change the code in UserRepository.

To make this more flexible, we can create an abstraction for the database connection:
```
//Abstract
interface DatabaseConnectionInterface
{
   public function connect();
}

//Low-level module
class MySqlConnection implements DatabaseConnectionInterface
{
   public function connect()
   {
       // connect to the mysql database
   }
}

//High-level module
class UserRepository 
{
    private $db;

    public function __construct(DatabaseConnectionInterface $db)
    {
        $this->db = $db;
    }
}
```
Now, the UserRepository class depends on the DatabaseConnectionInterface abstraction instead of the concrete implementation. This makes it a lot more flexible because if we want to change the database system, we can just create a new implementation of the DatabaseConnectionInterface and inject it into the UserRepository class.
