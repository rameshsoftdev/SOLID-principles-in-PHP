# What is open/closed principle in php with an example?
The Open/Closed Principle states that software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification. This simply means that a piece of code should be written in such a way that it can be easily extended without having to modify the existing code.

For example, say you have a class for calculating the cost of shipping a product. You could write the class so that it calculates the cost based on a predetermined set of parameters, such as weight and size of the product.

Now, if you want to add additional parameters to the calculation, you wouldn't have to modify the existing code. You could simply extend the class and add the additional parameters. This would ensure that the original code remains intact and unchanged.

Example:
```
<?php 

class ShippingCostCalculator { 
 
    protected $weight; 
    protected $size; 
 
    public function __construct($weight, $size) { 
        $this->weight = $weight; 
        $this->size = $size; 
    } 
 
    public function calculateCost() { 
        return $this->weight * $this->size; 
    } 
 
} 

// extending the class to add additional parameters 
class ExtendedShippingCostCalculator extends ShippingCostCalculator { 
 
    protected $distance; 
 
    public function __construct($weight, $size, $distance) { 
        parent::__construct($weight, $size); 
        $this->distance = $distance; 
    } 
 
    public function calculateCost() { 
        return parent::calculateCost() + ($this->distance * 0.50); 
    } 
 
}
```
