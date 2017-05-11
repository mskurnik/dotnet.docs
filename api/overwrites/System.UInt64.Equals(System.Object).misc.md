---
uid: System.UInt64.Equals(System.Object)
additional_notes.usage: *content
---

<p>Compiler overload resolution may account for an apparent difference in the behavior of the two <xref href="System.UInt64.Equals(System.UInt64)"></xref> method overloads. If an implicit conversion between the <code>obj</code> argument and a <xref href="System.UInt64"></xref> is defined and the argument is not typed as an <xref href="System.Object"></xref>, compilers perform an implicit conversion and call the <xref href="System.UInt64.Equals(System.UInt64)"></xref> method. Otherwise, they call the <xref href="System.UInt64.Equals(System.Object)"></xref> method, which always returns `false` if its <code>obj</code> argument is not a <xref href="System.UInt64"></xref> value. The following example illustrates the difference in behavior between the two method overloads. In the case of the <xref href="System.Byte"></xref>, <xref href="System.UInt16"></xref>, and <xref href="System.UInt32"></xref> values, the first comparison returns `true` because the compiler automatically performs a widening conversion and calls the <xref href="System.UInt64.Equals(System.UInt64)"></xref> method, whereas the second comparison returns `false` because the compiler calls the <xref href="System.UInt64.Equals(System.Object)"></xref> method.  
  
 [!code-csharp[System.UInt64.Equals#2](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.uint64.equals/cs/equalsoverl.cs#2)]
 [!code-vb[System.UInt64.Equals#2](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uint64.equals/vb/equalsoverl.vb#2)]</p>

