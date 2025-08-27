# ArrayList vs LinkedList

| **Aspect** | **ArrayList** | **LinkedList** |
|------------|---------------|----------------|
| **Data Structure** | Uses a dynamic array internally. | Uses a doubly linked list internally. |
| **Access / Search** | Faster (**O(1)** for index access) because it uses an array. | Slower (**O(n)**) because it must traverse nodes one by one. |
| **Insertion / Deletion** | Slower (**O(n)**) especially in the middle, because elements need shifting. | Faster (**O(1)**) if you already have a reference to the node. |
| **Memory** | Less memory overhead. | More memory overhead (due to storing pointers for previous and next nodes). |
| **Use Case** | Best when frequent access/search operations are required. | Best when frequent insertions/deletions are needed, especially in the middle. |
