# Week 1 & 2

### Topics Covered
- Variables
- Data Types
- Operators
- Input and Output

---

### Questions

#### 1. What happens if you declare a variable in C++ but do not initialize it?

#### 2. What will be the output of the following code? Why?
```cpp
int x = 5;
int y = 2;
double result = x / y;
std::cout << result;
```

#### 3. How would you write a program, with some arbitrary variables `x`, , `y`, and `z`, to check that `x` is greater than `y` and less than `z`?

#### 4. What will be the output of the following code? Why?
```cpp
int x = 5;
std::cout << x++ << " " << ++x;
```

#### 5. The voltage across a charging capacitor in an RC circuit is given by:
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
