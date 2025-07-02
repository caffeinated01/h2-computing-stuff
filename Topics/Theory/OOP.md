Object-Oriented Programming (OOP) is a programming paradigm that organizes software design around data, or objects, rather than functions and logic

# 1. Properties of OOP

In OOP, a program is viewed as a collection of interacting objects
- **Object**: Represents a real-world or abstract entity with its own data and actions
- **Attribute**: A piece of data describing an object
- **State**: The current values of an object's attributes
- **Method**: An action that an object can perform

# 2. Classes and Objects

- **Class**: A blueprint or template for creating objects. It defines the attributes and methods that its objects will have
- **Object (Instance)**: A specific instance created from a class. While all objects of a class share the same structure, they have their own unique state (attribute values)

> [!note] Analogy  
> A Class is like a cookie cutter. The Objects are the individual cookies made from it

# Class Diagram Format

A UML (Unified Modelling Language) Class Diagram visually represents a class

| Class Name                                           |
| ---------------------------------------------------- |
| **Attributes**<br>- <attribute 1>: data type<br>- …… |
| **Methods**<br>+ <method 1><br>+ ……<br>+ Display()   |
`Display()` method is always good to include in Class Diagrams

**Visibility Symbols**:  

| Symbol | Visibility | Access                                             |
| :----: | :--------- | :------------------------------------------------- |
| **+**  | Public     | Can be accessed from anywhere                      |
| **-**  | Private    | Can only be accessed from within the class itself  |
| **#**  | Protected  | Can be accessed by the class and its child classes |

> [!note] Important note for Class Diagrams
> In class diagrams for **inheritance**, the arrow points from the child **up to** the parent
 
# Instantiation

Instantiation is the process of creating an object (an instance) from a class

A **constructor** is a special method that is automatically called when an object is created. Its job is to initialise the object's attributes

# 3. Encapsulation

Encapsulation is the grouping of an object’s data (attributes) and actions (methods) together and hiding the internal details from the outside world

This is achieved through **information hiding**:
- **Private Attributes**: Cannot be accessed or modified directly from outside the class
- **Public Methods**: Provide a safe and controlled way to interact with the object's data

**Benefits of encapsulation**
- **Controlled Access**: Data is only accessible through public methods (also called getters and setters). This helps keep the data accurate and consistent
- **Accident Prevention:** Since other parts of the program can't directly touch the data, it's less likely that bugs or errors will occur from accidental changes
- **Easier Teamwork**: Makes it easier for different programmers to work on separate parts of a program without interfering with each other. Since each object hides its internal details, others only need to know how to use it, not how it works inside

**Getters & Setters**
- **Getter**: A public method used to safely **read** the value of a private attribute
- **Setter**: A public method used to safely **update** the value of a private attribute. Setters can include validation logic to ensure the new value is sensible

# 4. Inheritance

Inheritance is a mechanism where a **child class** acquires the properties and behaviours of an existing **parent class**
- **Purpose**: Promotes code reuse and creates a logical hierarchy
- **The "Is-a" Rule**: Use inheritance only when the child class has an "is-a" relationship with the parent class (e.g., a Car **is a** Vehicle, but a Vehicle is not necessarily a Car)

**Benefits of Inheritance**
- **Code Reuse**: Child classes inherit all methods from the parent, avoiding redundant code
- **Easier Maintenance**: Fixing a bug in a parent method automatically fixes it for all child classes
- **Logical Structure**: Models real-world relationships clearly
- **Code Generalisation**: Allows a derived class to inherit general attributes and methods from a base class, while adding its own specialised features. 

# 5. Polymorphism

Polymorphism is the ability of objects of different classes to respond to the same method call in their own unique way
- Achieved through **method overriding**, where a child class provides its own specific implementation of a method that it inherited from its parent class
- The method name and parameters must remain the same; only the behaviour changes

**Benefits of Polymorphism**
- **Simplified Code**: Allows you to treat a collection of different objects uniformly. You can call the same method on each
- **Greater Flexibility**: Objects can be treated similarly while behaving differently based on their specific type
- **Easier to Extend**: New classes can be added to the system easily. As long as they inherit from the same parent and implement the required methods, they will integrate seamlessly