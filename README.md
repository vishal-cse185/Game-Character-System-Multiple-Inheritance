# Character Management System (C++)

This project demonstrates **Object-Oriented Programming (OOP)** concepts in C++ using a character-based system inspired by gaming environments.

It models different types of characters such as Warriors, Mages, and Healers, along with hybrid classes like Paladin and BattleMage.

---

## 🎯 Key Features

- Abstract base class (`Character`)
- Pure virtual functions (polymorphism)
- Virtual inheritance to avoid ambiguity
- Hybrid inheritance (multiple inheritance)
- Method chaining (fluent interface)
- Dynamic behavior using overridden methods

---

## 🧠 OOP Concepts Used

- **Encapsulation** – Data and methods inside classes  
- **Abstraction** – Base class with virtual functions  
- **Inheritance** – Derived classes like Warrior, Mage, Healer  
- **Polymorphism** – Overriding `useSpecialAbility()`  
- **Virtual Inheritance** – Prevents multiple copies of base class  

---

## 🧩 Class Structure

### 🔹 Base Class
- `Character`
  - Attributes: name, level, health
  - Pure virtual function: `useSpecialAbility()`

---

### 🔹 Derived Classes
- `Warrior` → Attack power, weapons  
- `Mage` → Mana, spells  
- `Healer` → Potions  

---

### 🔹 Hybrid Classes
- `Paladin` → Warrior + Healer  
- `BattleMage` → Warrior + Mage  

---

## ⚙️ How to Compile & Run

```bash
g++ main.cpp -o program
./program
