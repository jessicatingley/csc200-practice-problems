# Week 4

### Topics Covered
- Functions
- Built-in Functions
- Command Line Arguments

---

### Comprehension Check

#### 1. What will be the output of the following C++ program?
```cpp
#include <iostream>
using namespace std;

void testFunction() {
    int x = 10;
    cout << "Inside function: " << x;
}

int main() {
    testFunction();
    cout << " Outside function: " << x << endl;
    return 0;
}
```

- ```Inside function: 10 Outside function: 10```

- ```Inside function: 10 Outside function: 0```
- #### ```Inside function: 10 Outside function: (compiler error)```
- ```Inside function: 10 Outside function: Undefined behavior```

Explanation: The variable ```x``` is declared inside ```testFunction()```, making it a local variable with function scope. 
```Once testFunction()``` finishes execution, ```x``` ceases to exist.
In ```main()```, the line ```cout << "Outside function: " << x << endl;``` tries to access ```x```, but ```x``` is not declared in ```main()```, leading to a compiler error.


#### 2. What will be the output of the following code when run with command line arguments ```./program 5 3.2```?
```cpp
int main(int argc, char* argv[]) {
    std::cout << argv[0] << " " << argv[1] << " " << argc << std::endl;
    return 0;
}
```
- #### ./program 5 3
- 5 3.2 3
- ./program 5.0 2
- program 5 3

Explanation: ```argv[0]``` is always the name of the program (```./program```).
```argv[1]``` is the first command-line argument (5).
```argv[2]``` is the second command-line argument (3.2).
```argc``` (argument count) is the total number of command-line arguments, including the program name. Here, ```argc = 3```.


#### 3. When writing a function to calculate power consumption (P = V²/R) in a circuit, which function prototype is MOST appropriate?
- ```void calculatePower(double voltage, double resistance)```
- ```int calculatePower(int voltage, int resistance)```
- #### ```double calculatePower(double voltage, double resistance)```
- ```float calculatePower(int voltage, int resistance)```

Explanation: ```double``` allows for high precision, which is necessary for accurate power calculations.
Both voltage and resistance are ```double```, ensuring precise arithmetic operations.
Returns ```double```, which is appropriate for power values.


