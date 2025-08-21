# String vs StringBuilder vs StringBuffer

| **Aspect**       | **String** | **StringBuilder** | **StringBuffer** |
|------------------|------------|-------------------|------------------|
| **Mutability**   | Immutable | Mutable | Mutable |
| **Thread Safety**| Not thread-safe | Not thread-safe | Thread-safe (synchronized) |
| **Performance**  | Slower in concatenation | Faster (no synchronization overhead) | Slower than StringBuilder due to synchronization |
| **Use Case**     | Use when data doesn’t change often (like constants, keys). | Use when data changes frequently and thread safety is not needed. | Use when data changes frequently and thread safety is needed. |

---

## Quick One-Liner for Interviews
- **String** ? Immutable.  
- **StringBuilder** ? Mutable, faster, not thread-safe.  
- **StringBuffer** ? Mutable, slower, but thread-safe.
