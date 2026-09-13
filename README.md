# Animal Guessing Game

A Java-based desktop application that identifies an animal by asking the user a sequence of questions about its characteristics. The project demonstrates core Object-Oriented Programming concepts through a class hierarchy of different animal types and provides an interactive graphical interface using Java Swing.

Developed as an Object-Oriented Programming project.

## Overview

This project implements a rule-based animal identification system. The application starts with a set of possible animals and progressively eliminates animals based on the user's answers.

The animal database is organized using an inheritance hierarchy. Different animal categories such as fish, crustaceans, mollusks, insects, reptiles, carnivores, and herbivores inherit common properties from their parent classes.

The application combines the OOP model with a Java Swing GUI to provide a complete interactive experience from the welcome screen through the final animal guess.

## Key Features

* **Interactive GUI** — Java Swing-based interface for navigating the game
* **Rule-based identification** — identifies animals through a sequence of characteristic-based questions
* **Object-oriented class hierarchy** — animals are organized through inheritance
* **Multiple animal categories** — aquatic and terrestrial animals with different characteristics
* **Progressive elimination** — each answer removes animals that do not match the selected characteristics
* **Animal images** — graphical animal representations are included in the project
* **Question-based navigation** — ten sequential questions are used to narrow down the possible result
* **Result display** — the application displays the identified animal through dedicated GUI result screens

## How It Works

### 1. Animal Classification

The project defines a base `Creature` class containing common information shared by different animals.

The hierarchy is divided into aquatic and terrestrial categories:

```text
Creature
├── Water
│   ├── Fish
│   ├── Crustacean
│   └── Mollusca
│
└── Terrestrial
    ├── Insect
    ├── Reptile
    ├── Carnivorus
    └── Herbivorous
```

This structure allows common properties and behaviors to be inherited while allowing specialized animal classes to define their own characteristics.

### 2. Animal Database

The `Case` class initializes the animals used by the application.

The current animal set includes:

```text
Dolphin
Shark
Octopus
Crab
Shrimp
Butterfly
Ant
Turtle
Lizard
Lion
Leopard
Cow
Deer
```

Each animal is associated with properties that are used during the identification process.

### 3. Question-Based Identification

The GUI presents a sequence of questions about the selected animal's characteristics.

The questions cover properties such as:

```text
Habitat
Diet
Number of legs
Exoskeleton
Scales
Speed
Predator characteristics
Domestication
Wings
Colony/social behavior
```

The user's answers are passed through the identification logic to eliminate animals that do not match the selected characteristics.

### 4. Candidate Selection

The `SelectionArray` class maintains the current set of possible animals.

Initially, all candidates are enabled:

```java
public static boolean[] select =
    {true, true, true, true, true, true, true,
     true, true, true, true, true, true};
```

As the user answers questions, incompatible animals are disabled.

For example, selecting a water-based habitat removes terrestrial candidates from consideration.

The process continues until the remaining candidate represents the program's final guess.

### 5. Result

After the question sequence is completed, the application determines the remaining animal and opens the corresponding result screen.

The project contains dedicated GUI result classes for several animals, including:

```text
Ant
Butterfly
Cow
Deer
Leopard
```

## GUI Flow

The graphical interface follows a sequential navigation structure:

```text
Welcome
   │
   ▼
Rules
   │
   ▼
Animal Selection
   │
   ▼
Question 1
   │
   ▼
Question 2
   │
   ▼
Question 3
   │
   ▼
Question 4
   │
   ▼
Question 5
   │
   ▼
Question 6
   │
   ▼
Question 7
   │
   ▼
Question 8
   │
   ▼
Question 9
   │
   ▼
Question 10
   │
   ▼
Animal Result
```

## OOP Concepts

### Inheritance

Inheritance is used to create relationships between general and specialized animal categories.

For example:

```java
public class Fish extends Water
```

`Fish` inherits common characteristics from `Water`, while `Water` itself inherits from `Creature`.

### Encapsulation

Animal-related information is stored inside the appropriate classes. Common attributes such as name, attribute, habitat, and type are maintained as class members.

### Polymorphism

Different subclasses implement their own versions of methods such as `printDetails()`.

This allows objects from different animal categories to provide category-specific behavior while sharing a common interface.

### Abstraction

Interfaces are used to define common operations such as `showAnswer()`.

The project contains the following interfaces:

```text
answer
Ans
```

These provide a common structure for displaying answers for different animal types.

### Method Overriding

Animal subclasses override inherited methods to provide behavior specific to their category.

Classes such as `Fish`, `Crustacean`, `Mollusca`, `Insect`, `Reptile`, `Carnivorus`, and `Herbivorous` demonstrate this approach.

## Architecture / Components

| Component              | Responsibility                             |
| ---------------------- | ------------------------------------------ |
| `Creature`             | Base class for common animal information   |
| `Water`                | Parent class for aquatic animals           |
| `Terrestrial`          | Parent class for land animals              |
| `Fish`                 | Represents fish-type animals               |
| `Crustacean`           | Represents crustacean animals              |
| `Mollusca`             | Represents mollusk animals                 |
| `Insect`               | Represents insects                         |
| `Reptile`              | Represents reptiles                        |
| `Carnivorus`           | Represents carnivorous terrestrial animals |
| `Herbivorous`          | Represents herbivorous terrestrial animals |
| `Case`                 | Initializes and manages animal cases       |
| `SelectionArray`       | Maintains possible animal candidates       |
| `Question1–Question10` | Handles the question and answer flow       |
| `Welcome`              | Application starting screen                |
| `RulesGui`             | Displays game rules                        |
| `Select`               | Handles animal/game selection              |
| `Guess`                | Handles the guessing stage                 |
| Animal GUI classes     | Display animal-specific result screens     |

## Project Structure

```text
src/
├── GUI/
│   ├── Welcome.java
│   ├── RulesGui.java
│   ├── Select.java
│   ├── SelectionArray.java
│   ├── Guess.java
│   ├── Question1.java
│   ├── Question2.java
│   ├── Question3.java
│   ├── Question4.java
│   ├── Question5.java
│   ├── Question6.java
│   ├── Question7.java
│   ├── Question8.java
│   ├── Question9.java
│   ├── Question10.java
│   ├── Ant.java
│   ├── Butterfly.java
│   ├── Cow.java
│   ├── Deer.java
│   └── Leopard.java
│
├── PrinciplesOfOOP/
│   ├── Creature.java
│   ├── Water.java
│   ├── Terrestrial.java
│   ├── Fish.java
│   ├── Crustacean.java
│   ├── Mollusca.java
│   ├── Insect.java
│   ├── Reptile.java
│   ├── Carnivorus.java
│   ├── Herbivorous.java
│   ├── Case.java
│   ├── Ans.java
│   ├── answer.java
│   ├── land.java
│   └── Main.java
│
└── Animal Images
```

## Tech Stack

* **Java** — core programming language and application logic
* **Java Swing** — graphical user interface
* **IntelliJ IDEA** — development environment
* **Object-Oriented Programming** — application architecture and animal modeling

## Results

The application provides a complete question-driven animal identification workflow. Starting from a set of possible animals, the system uses the user's answers to progressively reduce the candidate set and determine a final animal.

The project demonstrates how OOP principles can be applied to a practical interactive application rather than only isolated class examples.

## Challenges

* Designing a class hierarchy that represents different types of animals
* Connecting the OOP model with the GUI
* Maintaining the candidate selection state between questions
* Implementing the animal identification rules
* Managing navigation between multiple Swing windows
* Handling different animal categories and characteristics
* Connecting animal-specific result screens with the identification logic

## Team

| Member                   | Contributions                                                                      |
| ------------------------ | ---------------------------------------------------------------------------------- |
| **Shakib Hasan**         | GUI development, animal identification logic, Java development, OOP implementation |
| **Ashique Imam Hossain** | GUI development, animal identification logic, Java development, OOP implementation |
| **Sushama Roy**          | OOP implementation, animal classes, animal data/model development                  |

## Course Context

* **Project:** Object-Oriented Programming Project
* **Language:** Java
* **Framework:** Java Swing
* **Development Environment:** IntelliJ IDEA

## Future Work

Potential improvements include:

* Adding result GUI screens for all supported animals
* Improving the animal identification algorithm
* Adding more animals and characteristics
* Improving GUI design and navigation
* Adding a restart/play-again option
* Replacing the boolean selection array with a more scalable candidate-management system
* Adding input validation and exception handling
* Adding unit tests for the identification logic
* Improving project structure and code maintainability

## License

This project was developed for academic and educational purposes.

---

**Developed by Shakib Hasan, Ashique Imam Hossain, and Sushama Roy.**
