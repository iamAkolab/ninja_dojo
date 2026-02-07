# Design Patterns in Java – Study Notes

This repository contains concise study notes on major software design patterns with definitions, intent, structure, when to use them, and Java examples.

---

## 📚 Table of Contents

1. [Factory Pattern](#1-factory-pattern)
2. [Builder Pattern](#2-builder-pattern)
3. [Singleton Pattern](#3-singleton-pattern)
4. [Observer Pattern](#4-observer-pattern)
5. [Iterator Pattern](#5-iterator-pattern)
6. [Strategy Pattern](#6-strategy-pattern)
7. [Adapter Pattern](#7-adapter-pattern)
8. [Facade Pattern](#8-facade-pattern)
9. [Quick Comparison Summary](#quick-comparison-summary)

---
# Creational
## 1. Factory Pattern

### Definition
The **Factory Pattern** creates objects without exposing the instantiation logic to the client. It returns objects through a common interface.

### Intent
Encapsulate object creation and promote loose coupling.

### When to Use
- When object creation is complex
- When code should depend on interfaces, not concrete classes

### Structure
- Product (interface)
- Concrete Products
- Factory class

### ☕ Java Example

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Rectangle implements Shape {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

class ShapeFactory {
    public static Shape getShape(String type) {
        if (type.equalsIgnoreCase("circle")) return new Circle();
        if (type.equalsIgnoreCase("rectangle")) return new Rectangle();
        return null;
    }
}
```

---

## 2. Builder Pattern

### Definition
The **Builder Pattern** constructs complex objects step-by-step.

### Intent
Separate object construction from representation.

### When to Use
- Objects with many optional parameters
- Immutable objects

### Structure
- Builder class
- Product class

### ☕ Java Example

```java
class User {
    private String name;
    private int age;

    private User(Builder builder) {
        this.name = builder.name;
        this.age = builder.age;
    }

    public static class Builder {
        private String name;
        private int age;

        public Builder setName(String name) {
            this.name = name;
            return this;
        }

        public Builder setAge(int age) {
            this.age = age;
            return this;
        }

        public User build() {
            return new User(this);
        }
    }
}
```

---

## 3. Singleton Pattern

### Definition
Ensures a class has **only one instance** and provides global access.

### Intent
Control shared resources.

### When to Use
- Logging
- Configuration management
- Database connections

### ☕ Java Example (Thread-safe)

```java
class Singleton {
    private static Singleton instance;

    private Singleton() {}

    public static synchronized Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

---
# Behavioral
## 4. Observer Pattern

### Definition
Defines a **one-to-many dependency** so observers are notified automatically.

### Intent
Enable event-driven systems.

### When to Use
- Event systems
- GUI frameworks
- Notification systems

### ☕ Java Example

```java
import java.util.*;

interface Observer {
    void update(String message);
}

class Subscriber implements Observer {
    public void update(String message) {
        System.out.println("Received: " + message);
    }
}

class Publisher {
    private List<Observer> observers = new ArrayList<>();

    void addObserver(Observer o) {
        observers.add(o);
    }

    void notifyObservers(String msg) {
        for (Observer o : observers) {
            o.update(msg);
        }
    }
}
```

---

## 5. Iterator Pattern

### Definition
Provides a way to access elements of a collection sequentially without exposing its structure.

### Intent
Encapsulate traversal logic.

### When to Use
- Custom collections
- Multiple traversal strategies

### ☕ Java Example

```java
import java.util.Iterator;
import java.util.List;

class NameRepository implements Iterable<String> {
    private List<String> names = List.of("Alice", "Bob", "Charlie");

    public Iterator<String> iterator() {
        return names.iterator();
    }
}
```

---

## 6. Strategy Pattern

### Definition
Defines a family of algorithms and makes them interchangeable.

### Intent
Enable behavior selection at runtime.

### When to Use
- Multiple ways to perform a task
- Avoid large conditional statements

### ☕ Java Example

```java
interface PaymentStrategy {
    void pay(int amount);
}

class CreditCardPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid with credit card: " + amount);
    }
}

class PayPalPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid with PayPal: " + amount);
    }
}

class ShoppingCart {
    private PaymentStrategy strategy;

    public ShoppingCart(PaymentStrategy strategy) {
        this.strategy = strategy;
    }

    public void checkout(int amount) {
        strategy.pay(amount);
    }
}
```

---
# Structural
## 7. Adapter Pattern

### Definition
Allows incompatible interfaces to work together.

### Intent
Convert one interface into another expected by the client.

### When to Use
- Integrating legacy systems
- Third-party libraries

### Java Example

```java
interface MediaPlayer {
    void play(String file);
}

class AdvancedPlayer {
    void playMp4(String file) {
        System.out.println("Playing mp4: " + file);
    }
}

class MediaAdapter implements MediaPlayer {
    private AdvancedPlayer player = new AdvancedPlayer();

    public void play(String file) {
        player.playMp4(file);
    }
}
```

---

## 8. Facade Pattern

### Definition
Provides a simplified interface to a complex subsystem.

### Intent
Hide complexity and improve usability.

### When to Use
- Complex APIs
- Layered architecture

### ☕ Java Example

```java
class CPU {
    void start() { System.out.println("CPU started"); }
}

class Memory {
    void load() { System.out.println("Memory loaded"); }
}

class ComputerFacade {
    private CPU cpu = new CPU();
    private Memory memory = new Memory();

    public void startComputer() {
        cpu.start();
        memory.load();
    }
}
```

---

## Quick Comparison Summary

| Pattern   | Type       | Purpose                          |
|-----------|------------|----------------------------------|
| Factory   | Creational | Object creation abstraction      |
| Builder   | Creational | Step-by-step object construction |
| Singleton | Creational | Single shared instance           |
| Observer  | Behavioral | Event notification system        |
| Iterator  | Behavioral | Sequential collection traversal  |
| Strategy  | Behavioral | Interchangeable algorithms       |
| Adapter   | Structural | Interface compatibility          |
| Facade    | Structural | Simplify complex systems         |

---

## License

This content is provided for educational and learning purposes.

