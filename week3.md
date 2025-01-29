# Week 3

### Topics Covered
- Strings
- Arrays
- Standard Template Library
- Dynamic Memory Management

---

### Questions

#### 1. What is the difference between ```std::getline()``` and ```std::cin``` when reading a string?

#### 2. What will be the output of the following program? Why?
```cpp
#include <iostream>

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    std::cout << arr[5];
    return 0;
}
```

#### 3. How do you find the size of a ```std::vector```?

#### 4. What happens if you insert a duplicate into a ```std::set```?

#### 5. What happens if you allocate memory with ```new[]``` but release it with ```delete``` instead of ```delete[]```?

#### 6. The voltage across a charging capacitor in an RC circuit is given by:
#### Learning Objectives:
- Working with arrays and STL containers
- Basic string manipulation
- Dynamic memory allocation
- Understanding electrical engineering concepts

#### Background:
You are designing a simple circuit analysis tool. You have three basic components:
- A resistor (5 ohms)
- A capacitor (10 microfarads) 
- An inductor (2 millihenries)

#### Task: 
Create a C++ program that: 
- Creates an array to store these three component values 
- Uses std::string to store their units ("ohms", "microfarads", "millihenries")
- Uses std::vector to store component names ("resistor", "capacitor", "inductor")
- Calculates the total impedance magnitude at 1000Hz frequency  (The formula will be provided - just plug in the values)
- Stores the result in dynamically allocated memory

#### Example program output:
```
Circuit Components:
Resistor: 5 ohms
Capacitor: 10 microfarads
Inductor: 2 millihenries
Impedance at 1000Hz: 8.76 ohms
```
