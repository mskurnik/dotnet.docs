---
summary: Adds the specified content as the first children of this document or element.
remarks: "This method adds the new content before the existing content of the <xref:System.Xml.Linq.XContainer>.  \n  \n For details about the valid content that can be passed to this function, see [Valid Content of XElement and XDocument Objects](http://msdn.microsoft.com/library/aee2d319-5c5f-4b99-9bb4-2f58232577ae).  \n  \n This method will raise the <xref:System.Xml.Linq.XObject.Changed> and the <xref:System.Xml.Linq.XObject.Changing> events."
example:
- "The following example creates two XML trees, and then uses this method to add the results of a query to one of them.  \n  \n```csharp  \n  \n                XElement srcTree = new XElement(\"Root\",  \n    new XElement(\"Element1\", 1),  \n    new XElement(\"Element2\", 2),  \n    new XElement(\"Element3\", 3),  \n    new XElement(\"Element4\", 4),  \n    new XElement(\"Element5\", 5)  \n);  \nXElement xmlTree = new XElement(\"Root\",  \n    new XElement(\"NewElement\", \"Content\")  \n);  \nxmlTree.AddFirst(  \n    from el in srcTree.Elements()  \n    where (int)el >= 3  \n    select el  \n);  \nConsole.WriteLine(xmlTree);  \n```  \n  \n```vb  \n  \n                Dim srcTree As XElement = _   \n        <Root>  \n            <Element1>1</Element1>  \n            <Element2>2</Element2>  \n            <Element3>3</Element3>  \n            <Element4>4</Element4>  \n            <Element5>5</Element5>  \n        </Root>  \nDim xmlTree As XElement = <Root>  \n                              <NewElement>Content</NewElement>  \n                          </Root>  \nxmlTree.AddFirst( _  \n    From el In srcTree.Elements _  \n    Where CInt(el) >= 3 _  \n    Select el)  \nConsole.WriteLine(xmlTree)  \n  \n```  \n  \n This example produces the following output:  \n  \n```xml  \n  \n                <Root>  \n  <Element3>3</Element3>  \n  <Element4>4</Element4>  \n  <Element5>5</Element5>  \n  <NewElement>Content</NewElement>  \n</Root>  \n```"
uid: System.Xml.Linq.XContainer.AddFirst*
---