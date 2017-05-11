---
uid: System.Collections.ArrayList
thread_safety: *content
---

Public static (`Shared` in Visual Basic) members of this type are thread safe. Any instance members are not guaranteed to be thread safe.  
  
 An <xref href="System.Collections.ArrayList"></xref> can support multiple readers concurrently, as long as the collection is not modified. To guarantee the thread safety of the <xref href="System.Collections.ArrayList"></xref>, all operations must be done through the wrapper returned by the <xref href="System.Collections.ArrayList.Synchronized(System.Collections.IList)"></xref> method.  
  
 Enumerating through a collection is intrinsically not a thread-safe procedure. Even when a collection is synchronized, other threads can still modify the collection, which causes the enumerator to throw an exception. To guarantee thread safety during enumeration, you can either lock the collection during the entire enumeration or catch the exceptions resulting from changes made by other threads.

