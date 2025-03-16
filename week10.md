# Week 10

### Topics Covered
- Classes
- Objets
- Access Modifiers
- Friend Class and Function
- Default/Copy Constructors

---

### Comprehension Check


1. Which of the following statements about access modifiers is correct?
- **A `private` member can only be accessed within the same class.**
- A `public` member cannot be accessed outside the class.
- A `protected` member is accessible to all classes.
- `private` and `public` have the same access level.

Explanation:
`private` members can only be accessed within the class.
`public` members can be accessed anywhere.
`protected` members can be accessed in the same class and derived (child) classes.

2. What does the `this` pointer store?
- **The address of the object that calls a member function**
- The address of the first private member of the class
- The address of the class itself
- It is not a pointer

Explanation:
The this pointer holds the memory address of the current object in member functions.
It helps resolve conflicts between instance variables and function parameters with the same name.

3. What is the purpose of a copy constructor?
- To initialize an object with default values
- To delete an object from memory
- **To create a new object as a copy of an existing object**
- To prevent object copying
Explanation:
A copy constructor allows creating an object using another object’s values. This is useful when passing objects by value or returning objects from functions.

What is the correct way to declare a friend function?
```cpp
class A {
private:
    int data;
public:
    friend void showData(A obj);
};
```
- **Implementation is correct**
- `void A::showData(A obj);`
- `friend class showData(A obj);`
- Friend functions must be defined inside the class

Explanation:
The keyword `friend` allows a non-member function to access private members of the class.
The declaration must be inside the class but defined outside.

4. What will be the output of the following program?
```cpp
#include <iostream>
class Example {
    int x;
public:
    Example(int x) { this->x = x; }
    void show() { std::cout << x << std::endl; }
};

int main() {
    Example obj(10);
    obj.show();
    return 0;
}
```
- Compilation error
- **`10`**
- Garbage value
- Segmentation fault
Explanation:
The constructor `Example(int x)` uses `this->x = x;` to assign the value of the parameter `x` to the object's member variable `x`.
Since `obj` is initialized with `10`, calling `obj.show();` prints `10`.

5. What will be the output of the following code?
```cpp
#include <iostream>
class Test {
    int value;
public:
    Test(int v) { value = v; }
    Test(const Test& t) { value = t.value + 5; }
    void show() { std::cout << value << std::endl; }
};

int main() {
    Test obj1(10);
    Test obj2 = obj1;
    obj2.show();
    return 0;
}
```
- `10`
- `5`
- **`15`**
- Compilation error

Explanation:
`Test obj1(10);` creates an object `obj1` with `value = 10`.
`Test obj2 = obj1;` calls the copy constructor:
`Test(const Test& t) { value = t.value + 5; }`
Since `obj1.value = 10`, `obj2.value = 10 + 5 = 15`.
`obj2.show();` prints 15.

### Practice Problem
Problem Statement:
Create a Battery class that stores the charge level of a battery (0-100%). Implement the following:

A constructor that initializes the charge to a user-specified value.\
A member function useBattery(int amount) that reduces the charge.\
A member function showCharge() that prints the current charge.

#### Example Usage:
```
Battery b(50);  // Initialize with 50% charge
b.useBattery(10);
b.showCharge();  // Output: Battery Charge: 40%
```

#### Sample Solution:
```cpp
#include <iostream>
using namespace std;

class Battery {
private:
    int charge;

public:
    Battery(int c) { charge = c; }  // Constructor

    void useBattery(int amount) {
        charge -= amount;
        if (charge < 0) charge = 0;
    }

    void showCharge() {
        cout << "Battery Charge: " << charge << "%" << endl;
    }
};

int main() {
    Battery b(50);
    b.useBattery(10);
    b.showCharge();
    return 0;
}
```

