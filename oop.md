## Object-Oriented Programming
Object-Oriented Programming (OOP) is a programming paradigm that organizes code into objects, which are instances of classes. Python is an object-oriented language, and it supports all the core concepts of OOP, such as encapsulation, inheritance, polymorphism, and abstraction.
#### Key Concepts of OOP in Python:
- **Class:**
  - A blueprint for creating objects.
  - Defines attributes (data) and methods (functions) that the objects will have.
- **Object:**
  - An instance of a class.
  - Represents a specific entity with its own data and behavior.
- **Encapsulation:**
  - Bundling data (attributes) and methods (functions) that operate on the data into a single unit (class).
  - Restricting direct access to some of an object's components (using private/protected members).
  **How It Works:**
    - Use private attributes (e.g., self.__balance) to hide data.
    - Provide public methods to interact with the data (e.g., deposit, withdraw).  
  **Benefits:**
    - Improves security by preventing unauthorized access.
    - Makes code easier to maintain and modify.
    - Reduces complexity by hiding implementation details.
- **Inheritance:**
  - A mechanism where a new class (child class) derives properties and behaviors from an existing class (parent class).
  - Promotes code reuse and hierarchical classification.  
  **How It Works:**
    - Use the syntax class ChildClass(ParentClass) to inherit from a parent class.
    - Child classes can override or extend parent class methods.  
  **Benefits:**
    - Reduces code duplication.
    - Makes code more organized and easier to maintain.
    - Supports the "is-a" relationship (e.g., a Dog is an Animal).
- **Polymorphism:**
  - The ability of different classes to be treated as instances of the same class through a common interface.
  - Allows methods to behave differently based on the object that calls them.  
  **How It Works:**
    - Achieved through method overriding (child classes provide their own implementation of a method).
    - A single function or method can work with objects of different classes.  
  **Benefits:**
    - Simplifies code by allowing a single interface to represent different types.
    - Makes code more flexible and scalable.
    - Supports the "one interface, multiple implementations" principle.  
- **Abstraction:**
  - Hiding complex implementation details and exposing only the necessary features.
  - Achieved through abstract classes and interfaces.  
  **Key Points:**
    1. Abstract Class:
        - Cannot be instantiated directly.
        - Serves as a blueprint for other classes.
        - Ensures that subclasses implement specific methods.
    2. Abstract Methods:
        - Declared in the abstract class but have no implementation.
        - Must be implemented by any subclass.
    3. Concrete Class:
        - Inherits from the abstract class.
        - Provides implementations for all abstract methods.
    4. Abstraction:
        - Hides complex implementation details.
        - Exposes only the necessary features (e.g., area and perimeter methods).    
  **Why Use Abstraction?**
    - Enforces Structure: Ensures that subclasses adhere to a specific interface.
    - Improves Maintainability: Makes code easier to understand and modify.
    - Promotes Reusability: Common functionality is defined in the abstract class, and subclasses can reuse it.
#### Magic/Dunder Methods:
Python classes can define special methods (e.g., __init__, __str__, __add__) to enable operator overloading and other behaviors.
#### Why Use OOP in Python?
- Modularity: Code is organized into reusable components.
- Reusability: Inheritance allows code reuse.
- Maintainability: Easier to debug and maintain.
- Scalability: Suitable for large and complex applications.

Sample code: [Object-Oriented Programming](https://github.com/tamunoWoks/python_tutorial/blob/main/oop.ipynb)

