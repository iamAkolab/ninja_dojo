# Design Patterns Mastery – 2026 Edition

A practical, multi-language repository to learn, implement, and combine essential software design patterns — from foundational OOP to modern concurrency and architecture.

## 🧩 Pattern Categories
## 1. Creational Patterns
* Singleton: Ensures a single global instance.
* Factory Method: Creates objects without specifying classes.
* Builder: Constructs complex objects step-by-step.

## 2. Structural Patterns
** Adapter: Connects incompatible interfaces.
** Decorator: Dynamically adds functionalities.
** Facade: Simplifies complex subsystems.

## 3. Behavioral Patterns
* Observer: Notifies dependents of state changes.
* Strategy: Switches algorithms at runtime.
* Command: Encapsulates requests as objects.

## 4. Concurrency Patterns (Java specific)
* Thread Pool: Reuses threads for multiple tasks.
* Future/Promise: Manages async results.
* Blocking Queue: Safe producer-consumer handling.

## 5. Architectural Patterns
* MVC (Model-View-Controller): Separates data, UI, and logic layers.
* Microservices: Build applications as loosely coupled services.
* Event-Driven: Uses events for asynchronous communication.
  

1. **Creational** – Manage object creation  
   (`Singleton`, `Factory Method`, `Builder`)
2. **Structural** – Compose objects/classes  
   (`Adapter`, `Decorator`, `Facade`)
3. **Behavioral** – Assign responsibilities & communication  
   (`Observer`, `Strategy`, `Command`)
4. **Concurrency** – Handle parallelism safely  
   (`Thread Pool`, `Future/Promise`, `Blocking Queue`)
5. **Architectural** – System-level structure  
   (`MVC`, `Microservices`, `Event-Driven`)

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
