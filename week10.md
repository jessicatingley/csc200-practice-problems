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
