# Day 05: Collection Framework in Java

The **Collection Framework** in Java is a set of classes and interfaces that help us **store and manipulate groups of objects easily**.  
It provides **ready-made data structures** like `List`, `Set`, `Queue`, and `Map`, so we don’t have to write everything from scratch.

---

## **Main Interfaces in Collection Framework**

### **1. List**
- Stores **ordered elements**.
- **Allows duplicates**.  
**Examples:** `ArrayList`, `LinkedList`, `Vector`, `Stack`.

---

### **2. Set**
- Stores **unique elements**.
- **No duplicates allowed**.  
**Examples:** `HashSet`, `LinkedHashSet`, `TreeSet`.

---

### **3. Queue**
- Used for **FIFO (First In First Out)** or **priority-based processing**.  
**Examples:** `PriorityQueue`, `ArrayDeque`, `LinkedList`.

---

### **4. Map**
- Stores data as **key-value pairs**.
- **Keys are unique**, but **values can be duplicate**.  
**Examples:** `HashMap`, `LinkedHashMap`, `TreeMap`, `Hashtable`.

---

## **Hierarchy (Easy to Remember)**

Collection (Interface)
|--- List (Interface)
| |--- ArrayList, LinkedList, Vector, Stack
|
|--- Set (Interface)
| |--- HashSet, LinkedHashSet, TreeSet
|
|--- Queue (Interface)
|--- PriorityQueue, ArrayDeque

Map (Interface)
|--- HashMap, LinkedHashMap, TreeMap, Hashtable


## **Quick One-Liner for Interviews**

> **“Collection Framework in Java is a group of classes and interfaces that provide ready-made data structures like List, Set, Queue, and Map for storing and manipulating groups of objects efficiently.”**

