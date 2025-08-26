# **Day 09: Multithreading in Java**

---

## **1. What is Multithreading?**

Multithreading means executing **multiple parts of a program (threads) at the same time** for better performance.  

- Each thread runs **independently** but **shares the same memory space**.

---

## **2. Benefits of Multithreading**

- Better **CPU utilization**  
- **Faster execution** when multiple tasks run in parallel  
- Used in **gaming, servers, chat applications**, etc.

---

## **3. Lifecycle of a Thread**

A thread goes through **five main states**:

- **New (Created)** → Thread object is created.  
- **Runnable** → Ready to run, waiting for CPU.  
- **Running** → Actively executing.  
- **Waiting/Blocked** → Temporarily paused.  
- **Terminated (Dead)** → Finished execution.

---

## **4. Creating a Thread**

### **(a) Extending `Thread` class**

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running...");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start();
    }
}
```

---

### **(b) Implementing `Runnable` interface**

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread running...");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t = new Thread(new MyRunnable());
        t.start();
    }
}
```

---

## **5. Thread Methods**

| **Method** | **Description** |
|-------------|----------------|
| `start()` | Starts a thread. |
| `run()` | Contains the code to execute in the thread. |
| `sleep(ms)` | Pauses the thread for given milliseconds. |
| `join()` | Waits for another thread to finish. |
| `getName()` | Returns thread name. |
| `setPriority(int)` | Sets priority (1-10). |

---

## **6. Thread Priorities**

- **Min Priority** → `1`  
- **Normal Priority** → `5` (default)  
- **Max Priority** → `10`

---

## **7. Synchronization**

When multiple threads access **shared resources**, **data inconsistency** can occur.  
To handle this, we use **synchronized blocks or methods**.

**Example:**

```java
class Counter {
    int count = 0;
    synchronized void increment() {
        count++;
    }
}
```

---

## **8. Daemon Threads**

- Threads that run in the **background** for support tasks (like garbage collection).  
- Created using:

```java
thread.setDaemon(true);
```

---

## **9. Difference: Process vs Thread**

| **Aspect** | **Process** | **Thread** |
|-------------|------------|-------------|
| **Memory** | Separate | Shared |
| **Speed** | Slower | Faster |
| **Creation** | Heavy | Lightweight |

---

## 1️⃣ Difference between Extending Thread and Implementing Runnable

| Aspect | Extending Thread | Implementing Runnable |
|--------|----------------|-----------------------|
| **Inheritance** | Not flexible — you cannot extend any other class since Java does not support multiple inheritance. | Flexible — you can still extend another class while implementing Runnable. |
| **Code Reusability** | Less reusable — tightly couples task logic with the thread. | More reusable — separates task (logic) from thread execution. |
| **Object Handling** | Creates a separate object for each thread. | Multiple threads can share the same Runnable object. |
| **Preferred When** | You want to override other Thread methods directly. | You want better design and scalability. |



**Important Note:** Always prefer Runnable when designing large or
complex systems for better code reusability and flexibility.

------------------------------------------------------------------------

## 2️⃣ How to Handle Thread Synchronization

Thread synchronization is used to avoid data inconsistency when multiple
threads try to access a shared resource at the same time.

### a) Using synchronized method

``` java
class Counter {
    int count = 0;

    synchronized void increment() {
        count++;
    }
}

public class SyncExample {
    public static void main(String[] args) throws InterruptedException {
        Counter c = new Counter();

        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) c.increment();
        });

        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) c.increment();
        });

        t1.start();
        t2.start();

        t1.join();
        t2.join();

        System.out.println("Count: " + c.count);
    }
}
```

**Output:**

    Count: 2000

------------------------------------------------------------------------

### b) Using synchronized block

``` java
synchronized(object) {
    // critical section code
}
```

This gives more control by synchronizing only specific parts of the
code.

------------------------------------------------------------------------

## 3️⃣ What are Daemon Threads

A **daemon thread** is a background thread that provides services to
user threads.

It runs continuously but does not prevent the JVM from exiting once all
user threads finish.

### Example:

``` java
public class DaemonExample {
    public static void main(String[] args) {
        Thread t = new Thread(() -> {
            while (true) {
                System.out.println("Daemon thread running...");
            }
        });
        t.setDaemon(true); // Mark thread as daemon
        t.start();

        System.out.println("Main thread finished...");
    }
}
```

### Key Points:

-   Garbage Collector is a daemon thread.
-   Must call `setDaemon(true)` **before** `start()`, otherwise it
    throws `IllegalThreadStateException`.
-   JVM exits as soon as all non-daemon threads are done, even if daemon
    threads are running.
