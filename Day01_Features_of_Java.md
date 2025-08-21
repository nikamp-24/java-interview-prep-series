## What are the main features of Java, and why is it called platform independent?

Java has several key features that make it one of the most popular programming languages:

- **Object-Oriented** – Follows the four OOP principles: Encapsulation, Inheritance, Polymorphism, and Abstraction.  
- **Platform Independent** – Java code is compiled into bytecode, which can run on any system that has a JVM. This is why it’s known as *Write Once, Run Anywhere (WORA)*.  
- **Robust & Secure** – Strong memory management, garbage collection, and security features like the sandbox model and no explicit pointer use.  
- **Multithreaded** – Supports concurrent execution of multiple tasks within a program.  
- **High Performance** – Through Just-In-Time (JIT) compilation.  
- **Distributed** – Provides APIs for networking, RMI, and web services.  
- **Portable** – Same bytecode can be executed on different machines without changes.  

---

## 👉 Why Platform Independent?

Java doesn’t directly compile into machine code like C or C++. Instead, Java source code is compiled into **bytecode**.  
This bytecode is not specific to any operating system.  

The **JVM (Java Virtual Machine)** of each OS takes this bytecode and converts it into machine code that the OS understands.  

That’s why the same `.class` file can run on any machine which has a JVM → this is called **Write Once, Run Anywhere (WORA)**.

