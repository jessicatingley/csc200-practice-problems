# Week 1 & 2

### Topics Covered
- Variables
- Data Types
- Operators
- Input and Output

---

### Comprehension Check

#### 1. What happens if you declare a variable in C++ but do not initialize it?
- The variable is automatically initialized to zero.
- The program will not compile.
- #### The variable holds a random or garbage value.
- The variable cannot be declared without initialization.

Explanation: In C++, when you declare a variable without initializing it, the variable is allocated memory, but its value is undefined. This means the variable holds whatever random or "garbage" data happens to already be present at that memory location.


#### 2. What will be the output of the following code? Why?
```cpp
int x = 5;
int y = 2;
double result = x / y;
std::cout << result;
```
- 2.5
- #### 2.0
- 2
- Error

Explanation: The division between integers will result in an integer, and then it will be cast to a double .


#### 3. Write an expression using some arbitrary variables `x`, `y`, and `z` to check that `x` is greater than `y` and less than `z`?

#### Answer: x > y && x < z
Explanation: The problem states that x should be greater than y and less than z. In C++, the logical && operator ensures that both conditions are true simultaneously.


#### 4. What will be the output of the following code? Why?
```cpp
int x = 5;
std::cout << x++ << " " << ++x;
```
- #### 5 7
- 5 6
- 6 7
- Compilation Error

Explanation: ```x++``` increments after its value is used, and ```++x``` increments before its value is used.

#### Practice Problem
#### The voltage across a charging capacitor in an RC circuit is given by:
$$ V(t) = V_s \times \left(1 - e^{-\frac{t}{R \cdot C}}\right) $$

#### Where:
- \( V_s \): Source voltage (volts)
- \( t \): Time (seconds)
- \( R \): Resistance (ohms)
- \( C \): Capacitance (farads)

#### Write a program to determine the voltage across a capacitor in an RC circuit after a given time.
#### Example program output:
```
Enter source voltage (V_s): 10  
Enter resistance (R in ohms): 1000  
Enter capacitance (C in farads): 0.001  
Enter time (t in seconds): 2  
Voltage across the capacitor = 8.64818 volts
```
Example Solution:
```cpp
#include <iostream>
#include <cmath>  // For the exponential function

using namespace std;

int main() {
    // Declare variables for user input
    double V_s, R, C, t, V;

    // Prompt the user for inputs
    cout << "Enter source voltage (V_s): ";
    cin >> V_s;

    cout << "Enter resistance (R in ohms): ";
    cin >> R;

    cout << "Enter capacitance (C in farads): ";
    cin >> C;

    cout << "Enter time (t in seconds): ";
    cin >> t;

    // Calculate the voltage across the capacitor
    V = V_s * (1 - exp(-t / (R * C)));

    // Output the result
    cout << "Voltage across the capacitor = " << V << " volts" << endl;

    return 0;
}
```
