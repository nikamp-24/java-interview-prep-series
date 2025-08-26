## **Thread Lifecycle in Java**

A thread in Java goes through **5 main states**:

---

### **1️⃣ New (Created)**  
- A thread is created but **not started yet**.  
- Happens when you create a thread object using `Thread` class or `Runnable` interface.

```java
Thread t = new Thread();
```

---

### **2️⃣ Runnable**  
- When `start()` is called, the thread moves to the **Runnable state**.  
- It is **ready to run**, waiting for CPU to schedule it.

```java
t.start();
```

---

### **3️⃣ Running**  
- When the **CPU picks the thread** from the Runnable pool, it starts executing its `run()` method.

---

### **4️⃣ Waiting / Timed Waiting / Blocked**  
- Thread is **paused temporarily**.  

**Examples:**  
- `sleep(1000)` → Timed Waiting  
- `join()` → Waiting  
- Trying to access a locked resource → Blocked  

---

### **5️⃣ Terminated (Dead)**  
- Thread **completes execution** or is **stopped**.  
- Cannot be restarted again with `start()`; you need to **create a new thread object**.

---

## **Thread Lifecycle Diagram**

```
    New
     |
     v
  Runnable
     |
     v
  Running
   /   \
  v     v
Waiting  Blocked
     \   /
      v v
   Terminated
```

---

## **Example**

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class ThreadLifeCycle {
    public static void main(String[] args) {
        MyThread t = new MyThread(); // New
        t.start();                   // Runnable → Running
    }
}
```

---

## **Quick One-Liner for Interviews**

“A thread starts in **New**, moves to **Runnable**, then **Running** when scheduled, may enter **Waiting/Blocked**, and finally ends in **Terminated**.”
