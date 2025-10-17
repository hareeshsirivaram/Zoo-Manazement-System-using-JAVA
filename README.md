# Zoo Management System

A **Java-based console application** that allows users to manage animals in a zoo — specifically **Tigers, Penguins, and Dolphins**.  
This project demonstrates **Object-Oriented Programming (OOP) principles** and uses **Java Serialization** for persistent storage.

---

## Project Overview

The Zoo Management System allows a user to:

- Set and view each animal’s characteristics  
- Trigger their behaviors (walking, swimming, eating)  
- Save animal data to files (serialization)  
- Read back saved data from files (deserialization)  

### OOP Concepts Demonstrated
| Concept | Example |
|---------|---------|
| Abstraction | `Animal` abstract class + interfaces (`Eat`, `Walk`, `Swim`) |
| Inheritance | `Tiger`, `Penguin`, `Dolphin` extend `Animal` |
| Polymorphism | `Animal animal = new Tiger()` and overridden methods |
| Encapsulation | Private attributes with public getters/setters |
| Serialization | Saving and retrieving objects using `ObjectOutputStream` and `ObjectInputStream` |

---

## Modules and Their Purpose

| Module | Description |
|--------|-------------|
| `Animal.java` | Abstract superclass defining shared properties like name, age, height, weight, and behavior (`eatingFood`) |
| `Eat.java` | Interface ensuring animals define `eatingFood()` and `eatingCompleted()` |
| `Walk.java` | Interface defining `walking()` for animals that can walk |
| `Swim.java` | Interface defining `swimming()` for animals that can swim |
| `Tiger.java` | Extends `Animal`, implements `Walk`; defines tiger-specific attributes like stripes, speed, and roar level |
| `Dolphin.java` | Extends `Animal`, implements `Swim`; defines color and swimming speed |
| `Penguin.java` | Extends `Animal`, implements both `Walk` and `Swim`; defines walking/swimming speed and behavior |
| `Main.java` | Contains the main menu-driven logic — handles user input, file I/O, and object persistence |

---

## Program Flow

1. **Start Application**  
   The `Main` class runs and displays the main menu:  
  1. Tiger

  2. Dolphin

  3. Penguin

  4. Save animals to file

  5. Display saved animals from file

2. **Choose an Animal**  
Example: choosing “Tiger” creates a `Tiger` object and opens a sub-menu:  
1. Set properties

2. Display properties

3. Display movement

4. Display eating

3. **Perform Actions**  
- Set properties → user enters attributes (like stripes, speed)  
- Display properties → prints all stored values  
- Display movement → calls `walking()` or `swimming()`  
- Display eating → shows behavior like `"Tiger: I am eating meat."`  
4. **Save Animal Data**  
Animals are serialized to files like `tiger.txt`, `penguin.txt`, `dolphin.txt` using `ObjectOutputStream`.  
5. **Load Animal Data**  
Files are deserialized using `ObjectInputStream` and displayed with overridden `toString()` methods.

---

## Storage Concept

This project does **not use a database**.  
Instead, it uses **Java Serialization** to persist objects:

- Each file acts as a snapshot of an animal’s state.  
- Example: `tiger.txt` contains the serialized `Tiger` object.

---

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/<your-username>/ZooManagementSystem.git

1. Open the project in your preferred IDE (Eclipse/IntelliJ/NetBeans)

2. Run Main.java

3. Follow the on-screen menu to manage animals

Project Structure
ZooManagementSystem/
├─ src/
│  ├─ Main.java
│  ├─ models/         # Animal, Tiger, Dolphin, Penguin classes
│  ├─ interfaces/     # Eat, Walk, Swim
├─ data/              # Serialized files: tiger.txt, penguin.txt, dolphin.txt
├─ screenshots/       # Add your images here
└─ README.md
