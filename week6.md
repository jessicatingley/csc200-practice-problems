# Week 6

### Topics Covered
- For Loop
- While Loop
- Jump Statements

---

### Comprehension Check

#### 1. Identify the error in the code below:
```cpp
#include <iostream>
int main() {
    int i = 0;
    for (; i < 5;) {
        std::cout << i << " ";
    }
    return 0;
}
```
- It runs infinitely
- #### `i` is never incremented, causing an infinite loop
- The semicolon after `for` is incorrect
- There is no error

Explanation: The `for` loop is missing an increment statement, meaning `i` is never updated.
Since `i` starts at `0` and the loop condition is `i < 5`, it will always be true.
This results in an infinite loop.

#### 2. What is the output of the following loop?
```cpp
#include <iostream>

int main() {
    for (int i = 0; i < 5; i++) {
        if (i % 2 == 0) continue;
        std::cout << i << " ";
    }
    return 0;
}
```
- #### `1 3`
- `0 1 2 3 4`
- `0 2 4`
- `1 2 3 4`

Explanation: The `continue` statement skips the rest of the loop body whenever `i % 2 == 0` (i.e., when `i` is even).
The values of `i` that are even `(0, 2, 4)` are skipped, so only odd numbers `(1, 3)` are printed.

#### 3. What is the output of this loop?
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5;
    do {
        cout << x << " ";
        x--;
    } while (x > 0);
    return 0;
}
```
- `5 4 3 2 1 0`
- `5 4 3 2 1 -1`
- Infinite loop
- #### `5 4 3 2 1`

Explanation: The do-while loop executes at least once, even if the condition is false.
`x` starts at `5` and decrements each iteration.
The loop stops when `x` reaches `0`, so the last printed value is `1`.

#### 4. Which program will correctly print a final value of `5`?
- ```cpp
  #include <iostream>

  int main() {
      int count = 0;
      while (count < 5) {
          count++;
      }
      std::cout << count << endl;
      return 0;
  }
  ```
- ```cpp
  #include <iostream>

  int main() {
      int count = 0;
      for (int i = 0; i < 5; i++) {
          count += 2;
      }
      std::cout << count << endl;
      return 0;
  }
  ```
- ```cpp
  #include <iostream>

  int main() {
      int count = 0;
      do {
          count++;
      } while (count < 5);
      std::cout << count << endl;
      return 0;
  }
  ```
- ```cpp
  #include <iostream>

  int main() {
      int count = 0;
      for (int i = 0; i < 10; i++) {
          if (i % 2 == 0) {
              count++;
          }
      }
      std::cout << count << endl;
      return 0;
  }
  ```
Explanation: The `while` loop increments count until it reaches `5`, then stops.
The final value of `count` is correctly `5`.

#### 5. What is output by the following program?
```cpp
#include <iostream>

void printNumbers() {
    for (int i = 1; i <= 5; i++) {
        cout << i << " ";
        if (i == 3) return;
    }
    std::cout << "End";
}

int main() {
    printNumbers();
    return 0;
}
```
- `1 2 3 End`
- #### `1 2 3`
- `1 2 3 4 5 End`
- Compilation Error

Explanation: The loop prints numbers starting from `1`.
When `i == 3`, the `return` statement exits the function immediately.
`"End"` is never printed because the function terminates early.

### Practice Problem
#### LED Blinking Simulation
In embedded systems, LEDs are commonly controlled by microcontrollers using loops.

#### Task:
- Write a program that takes a number of blinks from the user.
- Use a function that prints "LED ON" and "LED OFF" alternately.
- Use a loop to call this function the correct number of times.
- If the user enters 0, exit the program.

#### Example Input/Output:
```
Enter number of blinks: 3
LED ON
LED OFF
LED ON
LED OFF
LED ON
LED OFF
```

#### Example Solution:
```cpp
#include <iostream>
using namespace std;

void blinkLED() {
    cout << "LED ON" << endl;
    cout << "LED OFF" << endl;
}

int main() {
    int blinks;
    
    cout << "Enter number of blinks (0 to exit): ";
    cin >> blinks;

    while (blinks > 0) {
        blinkLED();
        blinks--; // Decrement blinks
    }

    return 0;
}
```
