# Outlines

- OOP
- Class
- Object Instantiation
- Using object data/methods
- Method
- Constructor
- Keywords "this", "static", "final"
- Package
- Method in more details
  - Access modifiers
  - Getter & Setters
  - Passing method arguments
  - toString(),equals()

---

## **OOP (Object-Oriented Programming)**

### **Class**

- A **class** serves as a blueprint to create objects.
- Use the keyword: `new ClassName` to create an object.

```java
class Car { // Class definition
    int speed; // Object property
    int acc;   // Object property
}

class TransportSim {
    public static void main(String[] args) {
        Car a = new Car(); // Create object a
        Car b = new Car(); // Create object b
    }
}
```

---

### **OOP Concepts**

- View everything as an **object**.
- Four main principles:
  - **Encapsulation (Structure)** → Lecture 1
  - **Inheritance (Structure)** → Lecture 2
  - **Abstraction (Structure)** → Lecture 3
  - **Polymorphism (Behavior)** → Lecture 4

---

#### **Encapsulation / Information Hiding (Structure)**

- Determines what should or shouldn't be accessible to users.
- **Accessibility Modifiers**:
  - `+` **public**: Accessible from anywhere.
  - `#` **protected**: Accessible within the class and its subclasses.
  - `-` **private**: Accessible only within the class.

```java
class Car {
    private int speed;  // Private property
    private int acc;    // Private property

    // Public method to safely modify speed
    public void pushAcc() {
        speed = speed + acc;
    }
}

class TransportSim {
    public static void main(String[] args) {
        Car a = new Car();
        Car b = new Car();

        // a.speed = -555; // Not allowed (private)
        a.pushAcc(); // Allowed (public)
    }
}
```

---

#### **Abstraction (Structure)**

- Defines a **template** (all subclasses must follow).
- Example:
  - A **vehicle** has essential components like an engine and wheels.
    - A **Car**, **Motorcycle**, or **Truck** will also have these components.

---

#### **Inheritance (Structure)**

- Subclasses inherit properties and behaviors from an existing class.
- Example:
  - All **CP students** are **engineer students**.
    - Engineer students have certain attributes; CP students inherit these attributes.
    - CP students may have additional attributes that engineer students don’t have.
- Benefits: Reduces code duplication.

```java
class Vehicle {
    private int speed;
    private int acc;

    public void pushAcc() {
        speed = speed + acc;
    }
}

class Car extends Vehicle { // Car is a subclass of Vehicle
    // Car inherits all properties and methods from Vehicle
}
```

---

#### **Polymorphism (Behavior)**

- The same code behaves differently based on the object.
- Example:
  - **Class Pet** includes subclasses: `Cat`, `Dog`, and `Duck`.
    - `cat.speak()` → Meow!
    - `dog.speak()` → Woof!
    - `duck.speak()` → Quack!

```java
class Pet {
    public void speak() {
        System.out.println("Some generic pet sound!");
    }
}

class Cat extends Pet {
    @Override
    public void speak() {
        System.out.println("Meow!");
    }
}

class Dog extends Pet {
    @Override
    public void speak() {
        System.out.println("Woof!");
    }
}

class Duck extends Pet {
    @Override
    public void speak() {
        System.out.println("Quack!");
    }
}

public class Main {
    public static void main(String[] args) {
        Pet myPet = new Dog();
        myPet.speak(); // Output: Woof!
    }
}
```

---
