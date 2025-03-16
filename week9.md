# Week 9

### Topics Covered
- Pointers
- References
- Dangling, null, wild pointers
- `nullptr`

---

### Comprehension Check

#### 1. Which of the following correctly declares and initializes a pointer to an integer?:
```cpp
int x = 10;
```
- **`int *ptr = &x;`**
- `int ptr = &x;`
- `int* ptr = 10;`
- `int *ptr; ptr = nullptr;`

Explanation: A is correct because it properly assigns the address of `x` to `ptr`.
B is incorrect because ptr is declared as an `int`, but `&x` is an address.
C is incorrect because a pointer cannot be assigned a direct integer value.
D is not initializing `ptr` to point to `x`, so it's not useful in this context.

#### 2. What does the following code print?
```cpp
int a = 42;
int *p = &a;
*p = 10;
std::cout << a;
```
- `42`
- **`10`**
- Memory error
- Compiler error

Explanation: `p` stores the address of `a`.
`*p = 10;` changes the value at `a`'s address to `10`.
`std::cout << a;` now prints `10`, since a was modified through the pointer.

#### 3. Which of the following causes a dangling pointer?
- `int *p = nullptr;`
- **`int *p = new int(10); delete p;`**
- `int x = 5; int &ref = x;`
- `int *p = &x;`

Explanation:
A dangling pointer occurs when a pointer still holds the address of a memory location that has been deallocated. 
In option B, the pointer `p` is pointing to dynamically allocated memory, but after delete `p`;, it still stores the (now invalid) address, causing undefined behavior if accessed.

#### 4. What is the purpose of nullptr in C++?
- A pointer to an undefined address.
- **A replacement for NULL to represent an invalid pointer.**
- Used only in function pointers.
- It allocates memory dynamically.

Explanation:
`nullptr` was introduced in `C++11` as a type-safe alternative to `NULL`.
Unlike `NULL`, which is typically defined as `0`, `nullptr` is specifically recognized as a pointer type, making it more robust in function overloads and type-checking.

#### 5. What happens when you try to dereference a null pointer?
```cpp
int *ptr = nullptr;
std::cout << *ptr;
```
- **Causes a segmentation fault (runtime error)**
- Prints `nullptr`
- Compiles but prints 0
- Causes a compiler error

Explanation:
Dereferencing nullptr leads to undefined behavior, typically causing a segmentation fault (runtime error).
The compiler may not catch this issue, but when executed, the program crashes because it tries to access memory that does not exist.

#### 6. What does the following code output?
```cpp
int a = 5, b = 10;
int *p = &a;
p = &b;
std::cout << *p;
```
- `5`
- Memory error
- Compiler error
- **`10`**

Explanation:
`p` is first assigned the address of `a`, but it is later reassigned to `&b`.
When we print `*p`, it now points to `b`, so it prints `10`.
