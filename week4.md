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


#### 4. What is the output of the following program?
```cpp
#include <iostream>
using namespace std;

void myFunction() {
    cout << "Hello, World!" << endl;
    return 5;
}

int main() {
    int x = myFunction();
    cout << "x = " << x << endl;
    return 0;
}
```
- ```
  Hello, World!
  x = 5
  ```
- ```
  Hello, World!
  x = 0
  ```
- Undefined behavior
- #### Compilation error

Explanation: The function ```myFunction()``` is declared with a ```void``` return type but attempts to return an ```int```. This results in a compilation error.


#### 5. What will be the output of the following C++ program?
```cpp
#include <iostream>
using namespace std;

void compute(int x, int y = 10) {
    cout << x * y << endl;
}

int main() {
    compute(5);
    compute(5, 2);
    return 0;
}
```
- ```
  50  
  10
  ```
- ```
  50
  50
  ```
- ```
  10
  10
  ```
- ```
  10
  50
  ```

Explanation: A. The first call ```compute(5);``` uses the default value of ```y = 10```, so ```5 * 10 = 50```.
The second call ```compute(5, 2);``` overrides the default value and uses ```y = 2```, so ```5 * 2 = 10```.
