# Design Patterns
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

```
backend-skills-2026/
├── README.md                     # Overview, goals, weekly roadmap
├── .gitignore                    # Ignore IDE/cache files
├── docs/
│   ├── architecture.md           # System diagrams, decisions
│   └── patterns.md               # Design pattern summaries + code examples
├── week-01/
│   ├── README.md                 # Weekly goals & reflection
│   ├── api-design/
│   │   ├── rest-vs-grpc.md
│   │   └── versioning-strategy.md
│   └── patterns/
│       ├── singleton.go          # Implementation
│       └── factory-method.py
├── week-02/
│   ├── README.md
│   ├── data-management/
│   │   ├── indexing-tuning.sql
│   │   └── sharding-demo.md
│   └── patterns/
│       ├── adapter.py
│       └── decorator.go
├── week-03/
│   ├── README.md
│   ├── concurrency/
│   │   ├── async-pipelines.py
│   │   └── structured-concurrency.md
│   └── patterns/
│       ├── observer.js
│       └── strategy.go
├── week-04/
│   ├── README.md
│   ├── distributed-systems/
│   │   ├── kafka-consumer-idempotent.py
│   │   └── service-mesh-config.yaml
│   └── patterns/
│       ├── thread-pool.rs        # Rust example
│       └── event-driven-arch.md
├── projects/
│   └── trading-agent-backend/    # Your main project integrating all skills
│       ├── main.go
│       ├── Dockerfile
│       ├── k8s/
│       └── telemetry/
└── utils/
    ├── setup.sh                    # Install tools, start local Kafka/Redis
    └── review-checklist.md         # Weekly self-audit
```
