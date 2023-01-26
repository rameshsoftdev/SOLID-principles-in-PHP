# What is interface segregation in SOLID principle with example ?
Interface Segregation Principle (ISP) states that no client should be forced to depend on methods it does not use. This principle is intended to keep a system decoupled and thus easier to maintain and extend. It suggests that large interfaces should be split into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them.

For example, suppose we have an interface that contains methods related to both user and admin functionality:
```
interface UserAdminInterface {
    public function getUserDetails();
    public function getAdminDetails();
    public function updateUserDetails();
    public function updateAdminDetails();
}
```
We can split this interface into two separate interfaces, one for user and one for admin, to better adhere to the interface segregation principle:
```
interface UserInterface {
    public function getUserDetails();
    public function updateUserDetails();
}

interface AdminInterface {
    public function getAdminDetails();
    public function updateAdminDetails();
}
```
