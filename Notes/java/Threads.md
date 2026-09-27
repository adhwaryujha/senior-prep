Threads:
- basically a thread is sort of worker. java opens a thread which is responsible executing a sequence of instructions in your application.
- so java also introduces the concept of multi-threading, i.e. multiple workers can work on a data simulataneously which increases the efficiency and speed.
- Synchronised and Unsyncronized
    - Synchronized: This is one of Java's mechanisms to enforce thread safety. If a method or block of data is synchronized, it acts like a locked door. Only one thread can enter and make changes at a time, while the others wait in a queue. It guarantees safety but creates a severe performance bottleneck (which is why HashTable is notoriously slow).
    - Un-synchronized: There are no locks. Multiple threads can read and write at the exact same time. This makes the data structure incredibly fast (like HashMap), but if multiple threads modify it concurrently, the application will throw errors or corrupt the data.

-  
