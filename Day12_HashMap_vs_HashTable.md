# HashMap vs Hashtable in Java

| Aspect | HashMap | Hashtable |
|---------|---------|-----------|
| **Thread Safety** | Not synchronized (Not thread-safe) | Synchronized (Thread-safe, can be used in multi-threaded code) |
| **Null Keys / Values** | Allows 1 null key and multiple null values | Doesn’t allow any null key or value |
| **Performance** | Faster because no synchronization overhead | Slower due to synchronization |
| **Introduced In** | Java 1.2 (part of Collections Framework) | Java 1.0 (Legacy class) |
| **Use Case** | When thread safety is not required | When thread safety is required without external synchronization |
