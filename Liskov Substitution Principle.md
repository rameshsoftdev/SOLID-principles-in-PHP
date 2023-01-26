# What is Liskov Substitution principle with an example in php?
The Liskov Substitution Principle (LSP) states that any subclass or derived class should be substitutable for their base or parent class. This means that you should be able to use the derived class anywhere you would use the base class and have the same expected result.

For example, in PHP, let's assume we have a base parent class called 'Vehicle' and a derived class called 'Car'. The Car class extends Vehicle, so Car inherits any properties and methods that Vehicle has. This satisfies the Liskov Substitution Principle because if we have a function that takes a Vehicle object as an argument, we can pass it a Car object and the function will still work.
```
// Vehicle class
class Vehicle
{
    public function move()
    {
        // Move the vehicle
    }
}

// Car class
class Car extends Vehicle
{
    public function accelerate()
    {
        // Accelerate the Car
    }
}

// Function to move a vehicle
function moveVehicle(Vehicle $vehicle)
{
    $vehicle->move();
}

// Create a car
$myCar = new Car();

// Pass the car to the moveVehicle function
moveVehicle($myCar); // This will work because Car is substitutable for Vehicle
```
