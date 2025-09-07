# Static Keyword in Java

---

## 1️⃣ Static Variable
- A variable declared with the `static` keyword inside a class.  
- **Shared among all objects** of the class (only one copy exists).  
- Used for values common to all objects, like a counter.  

**Example:**
```java
class Counter {
    static int count = 0;
    Counter() {
        count++;
    }
}
```

---

## 2️⃣ Static Method
- Declared with `static` keyword.  
- Belongs to the **class**, not an object.  
- Can be called without creating an object.  
- Can only access **static variables and static methods** directly.  

**Example:**
```java
class Demo {
    static void show() {
        System.out.println("Static method called");
    }
}

public class Main {
    public static void main(String[] args) {
        Demo.show();  // Calling without object
    }
}
```

---

## 3️⃣ Static Block
- A block of code inside a class declared with `static`.  
- Executes **only once** when the class is loaded into memory.  
- Mostly used for initializing static variables.  

**Example:**
```java
class Test {
    static int num;
    static {
        num = 100;
        System.out.println("Static block executed");
    }
}
```

---

## One line answer
- A **static variable** is shared among all objects of a class.  
- A **static method** belongs to the class and can be called without creating an object.  
- A **static block** runs only once when the class is loaded, typically used to initialize static data.  
