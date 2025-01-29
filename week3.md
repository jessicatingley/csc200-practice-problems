# Week 3

### Topics Covered
- Strings
- Arrays
- Standard Template Library
- Dynamic Memory Management

---

### Comprehension Check

#### 1. What is the difference between ```std::getline()``` and ```std::cin``` when reading a string?
- ```std::cin``` reads an entire line, while ```std::getline()``` stops at whitespace.
- #### ```std::getline()``` reads an entire line, while ```std::cin``` stops at whitespace.
- There is no difference; both read input the same way.
- ```std::getline()``` can only read input from files, while ```std::cin``` reads from standard input.

Explanation: ```std::cin``` (using >> operator) reads only until the first whitespace (space, tab, newline). If you input "Hello World", ```std::cin >> str```; will only store "Hello" in str. ```std::getline()```  reads the entire line until a newline (\n) is encountered. If you input "Hello World", ```std::getline(std::cin, str)```; will store "Hello World" in str.



#### 2. What will be the output of the following program? Why?
```cpp
#include <iostream>

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    std::cout << arr[5];
    return 0;
}
```
- 5
- 0
- Compilation Error
- #### Undefined Behavior

Explanation: In C++, array indices start at 0, so the valid indices for ```arr[]``` (which has 5 elements) are ```arr[0]``` to ```arr[4]```.  The code attempts to access ```arr[5]```, which is out of bounds because it refers to memory beyond the array’s allocated space. Accessing an out-of-bounds index results in undefined behavior (UB), meaning the program may: crash, print a garbage value, exhibit unpredictable behavior, sometimes appear to "work" but remain incorrect.



#### 3. How do you find the size of a ```std::vector```?
- Use the ```.length()``` method of the ```std::vector```.
- Use the ```sizeof()``` operator on the ```std::vector```.
- #### Use the ```.size()``` method of the ```std::vector```.
- Use the ```.capacity()``` method of the ```std::vector```.

Explanation: ```std::vector``` is a dynamic array container in C++ that provides member functions for accessing its properties. To find the number of elements currently stored in a ```std::vector```, the ```.size()``` method is used.



#### 4. What happens if you insert a duplicate into a ```std::set```?
- The duplicate element is inserted, and the ```std::set``` allows multiple occurrences.
- The duplicate element replaces the existing one.
- The program throws a runtime error due to duplicate insertion.
- #### The duplicate element is ignored, and the ```std::set``` remains unchanged.

Explanation: A ```std::set``` in C++ only stores unique elements and automatically sorts them. If you attempt to insert a duplicate value, the ```std::set``` ignores the insertion, and the existing element remains. The size of the ```std::set``` does not change when a duplicate is inserted.



#### 5. What happens if you allocate memory with ```new[]``` but release it with ```delete``` instead of ```delete[]```?
- #### Undefined behavior occurs, which may lead to memory leaks or runtime errors.
- The memory is properly deallocated, and the program works correctly.
- The program will throw a compilation error.
- The program automatically corrects the mistake and uses ```delete[]```.

Explanation: In C++, ```new[]``` is used to allocate memory for an array, and ```delete[]``` must be used to properly release that memory. When you use delete instead of ```delete[]```, only the memory for the first element of the array is released, and the destructors for the remaining elements (if they exist) are not called.



### Practice Problem
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

#### Example Solution:
```cpp
#include <iostream>
#include <array>
#include <vector>
#include <string>
#include <cmath>

int main() {
    // Component values
    std::array<double, 3> values = {5.0, 10.0, 2.0};
    
    // Component units using std::string
    std::array<std::string, 3> units = {"ohms", "microfarads", "millihenries"};
    
    // Component names using std::vector
    std::vector<std::string> names = {"Resistor", "Capacitor", "Inductor"};
    
    // Constants for calculation
    const double PI = 3.14159265359;
    const double FREQ = 1000.0; // 1000 Hz
    
    // Calculate impedance components
    double* impedance = new double;  // Dynamic memory allocation
    
    double R = values[0];  // Resistance
    double C = values[1] * 1e-6;  // Convert µF to F
    double L = values[2] * 1e-3;  // Convert mH to H
    
    // Calculate impedance magnitude at 1000Hz
    // |Z| = sqrt(R^2 + (ωL - 1/(ωC))^2)
    double omega = 2 * PI * FREQ;
    *impedance = sqrt(R*R + pow(omega*L - 1.0/(omega*C), 2));
    
    // Output results
    std::cout << "Circuit Components:" << std::endl;
    std::cout << names[0] << ": " << values[0] << " " << units[0] << std::endl;
    std::cout << names[1] << ": " << values[1] << " " << units[1] << std::endl;
    std::cout << names[2] << ": " << values[2] << " " << units[2] << std::endl;
    std::cout << "Impedance at 1000Hz: " << *impedance << " ohms" << std::endl;
    
    // Clean up dynamic memory
    delete impedance;
    
    return 0;
}
```
