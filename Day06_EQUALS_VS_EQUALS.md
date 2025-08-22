# Day 06: == vs .equals() in Java

In Java, `==` and `.equals()` are used to compare objects, but they serve different purposes.  

---

## **Comparison Table**

| Aspect               | `==`                                                                  | `.equals()`                                                              |
|----------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------|
| **What it compares** | Compares references (whether both objects point to the same memory) | Compares content/value of objects (depends on `.equals()` implementation) |
| **Used for**         | Primitive types (`int`, `char`, etc.) or object references           | Objects (`String`, custom objects, etc.)                                  |
| **Default behavior** | Checks memory/reference equality                                      | By default (in `Object` class) checks reference equality; many classes like `String` override it to check value equality |
| **Example**          | `String a = new String("Hi"); String b = new String("Hi"); a == b ? false` | `a.equals(b) ? true`                                                      |

---

## **Example Code**

```java
String s1 = new String("Hello");
String s2 = new String("Hello");

System.out.println(s1 == s2);       // false (different memory)
System.out.println(s1.equals(s2));  // true  (same value)
Interview Tip
“Use == to check if two references point to the same object, use .equals() to check if two objects have the same value.”
