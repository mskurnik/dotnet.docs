---
summary: Selects the first `XmlNode` that matches the XPath expression.
remarks: "XPath expressions can include namespaces. Namespace resolution is supported using the `XmlNamespaceManager`. If the XPath expression includes a prefix, the prefix and namespace URI pair must be added to the `XmlNamespaceManager`.  \n  \n> [!NOTE]\n>  If the XPath expression does not include a prefix, it is assumed that the namespace URI is the empty namespace. If your XML includes a default namespace, you must still add a prefix and namespace URI to the `XmlNamespaceManager`; otherwise, you will not get any nodes selected. For more information, see [Select Nodes Using XPath Navigation](~/docs/standard/data/xml/select-nodes-using-xpath-navigation.md)."
example:
- "The following example returns the first book with the matching author name. The `XmlNamespaceManager` resolves the default namespace in the XPath expression.  \n  \n [!code-cpp[XmlNode.SelectSingleNode2#1](~/samples/snippets/cpp/VS_Snippets_Data/XmlNode.SelectSingleNode2/CPP/XmlNode.SelectSingleNode2.cpp#1)]\n [!code-csharp[XmlNode.SelectSingleNode2#1](~/samples/snippets/csharp/VS_Snippets_Data/XmlNode.SelectSingleNode2/CS/selectsingnode2.cs#1)]\n [!code-vb[XmlNode.SelectSingleNode2#1](~/samples/snippets/visualbasic/VS_Snippets_Data/XmlNode.SelectSingleNode2/VB/selectsingnode2.vb#1)]  \n  \n The example uses the file, `newbooks.xml`, as input.  \n  \n [!code-xml[XmlNode.SelectSingleNode2#2](~/samples/snippets/xml/VS_Snippets_Data/XmlNode.SelectSingleNode2/XML/newbooks.xml#2)]"
uid: System.Xml.XmlNode.SelectSingleNode*
---