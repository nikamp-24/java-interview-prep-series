# ArrayList vs Vector in Java

| **Aspect** | **ArrayList** | **Vector** |
|------------|---------------|-------------|
| **Thread Safety** | Not synchronized → Faster but not thread-safe. | Synchronized → Thread-safe but slower. |
| **Performance** | Better performance in single-threaded applications. | Slower due to synchronization overhead. |
| **Growth** | Increases size by 50% when more space is needed. | Increases size by 100% (doubles capacity). |
| **Usage** | Best for non-threaded applications. | Best for multi-threaded applications where thread safety is needed. |
| **Legacy** | Part of Java Collections Framework since Java 1.2. | Legacy class from Java 1.0, but still supported. |

---



> "ArrayList and Vector both store elements dynamically and allow duplicates. The main difference is that Vector is synchronized, so it's thread-safe but slower. ArrayList is not synchronized, so it's faster and commonly used in single-threaded applications. Also, Vector is a legacy class, while ArrayList is the modern preferred choice."
>
> ### If you have to design a program where multiple threads are reading and writing to a list at the same time, which would you prefer — ArrayList or Vector? And why?
>
> "I would prefer Vector over ArrayList in a multi-threaded environment because Vector is synchronized. This means it provides thread safety — only one thread can access the Vector at a time, preventing data inconsistency issues.
However, in modern applications, we often prefer using Collections.synchronizedList() with ArrayList or CopyOnWriteArrayList from java.util.concurrent for better performance and flexibility."
