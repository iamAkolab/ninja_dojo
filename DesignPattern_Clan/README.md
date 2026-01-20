# Design Patterns Mastery – 2026 Edition

A practical, multi-language repository to learn, implement, and combine essential software design patterns — from foundational OOP to modern concurrency and architecture.

---

## 🎯 Pattern Categories

#### 1. Creational Patterns – Manage object creation  
- **Singleton**: Ensures a single global instance.  
- **Factory Method**: Creates objects without specifying concrete classes.  
- **Builder**: Constructs complex objects step-by-step with fine-grained control.


#### 2. Structural Patterns – Compose objects and classes  
- **Adapter**: Connects incompatible interfaces to work together.  
- **Decorator**: Dynamically adds responsibilities to an object without subclassing.  
- **Facade**: Provides a simplified interface to a complex subsystem.


#### 3. Behavioral Patterns – Assign responsibilities and communication  
- **Observer**: Notifies dependent objects of state changes (publish-subscribe).  
- **Strategy**: Enables switching algorithms or behaviors at runtime.  
- **Command**: Encapsulates a request as an object, supporting queuing, logging, and undo.


#### 4. Concurrency Patterns – Handle parallelism safely  
> *Originally Java-centric, but applicable across modern languages.*  
- **Thread Pool**: Reuses a fixed set of threads to execute multiple tasks efficiently.  
- **Future / Promise**: Represents the result of an asynchronous computation.  
- **Blocking Queue**: Coordinates safe producer-consumer communication with built-in synchronization.

#### 5. Architectural Patterns – Define system-level structure  
- **MVC (Model-View-Controller)**: Separates data (Model), presentation (View), and logic (Controller).  
- **Microservices**: Structures an application as a collection of loosely coupled, independently deployable services.  
- **Event-Driven Architecture**: Uses events to trigger and communicate between decoupled components asynchronously.

---

## 🌐 Multi-Language Support
Each pattern includes implementations in:
- **Go** (for performance & concurrency)
- **Python** (for rapid prototyping & AI integration)
- **Java** (for enterprise & concurrency reference)

> 💡 *Concurrency patterns are labeled "Java-specific" in source material but implemented idiomatically in all three.*

## 🚀 Getting Started
```bash
cd creational/singleton/go
go run main.go
