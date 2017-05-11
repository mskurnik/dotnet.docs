---
uid: System.Windows.Freezable.GetAsFrozenCore(System.Windows.Freezable)
additional_notes.overrides: *content
---

<p>If you derive from <xref href="System.Windows.Freezable"></xref> you may need to override this method. Reasons to override include the following:  
  
-   Your derived class has data that is not exposed via dependency properties.  
  
-   Your derived class must perform extra initialization work that cannot be accomplished by simply overriding <xref href="System.Windows.Freezable.CreateInstanceCore"></xref>. For example, this applies if your derived class implements <xref href="System.ComponentModel.ISupportInitialize"></xref>.  
  
 Classes that store all their data in dependency properties and that do not need to perform extra initialization work do not need to override <xref href="System.Windows.Freezable.GetAsFrozenCore(System.Windows.Freezable)"></xref>.  
  
 It is essential that all implementations call the base implementation of this method. Implementations should only perform work that is not performed by the default implementation. The default implementation makes deep copies of any unfrozen freezables and shallow copies of all other writable, locally set properties it contains. If the object has data-bound dependency properties, the expressions are copied but might no longer resolve; for more information about cloning data-bound objects, see [Freezable Objects Overview](~/docs/framework/wpf/advanced/freezable-objects-overview.md). If the object has animated dependency properties, the base (non-animated) values of those properties are copied. Animations are not copied.  
  
 Note that unset properties are not copied, nor are read-only properties.  
  
 If you do override this method, you must call the base implementation.  
  
 You do not need to <xref href="System.Windows.Freezable.Freeze"></xref> values as they are copied.  The result is frozen by <xref href="System.Windows.Freezable.GetAsFrozen"></xref> before being returned.</p>

