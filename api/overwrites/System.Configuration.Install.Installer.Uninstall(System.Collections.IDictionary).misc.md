---
uid: System.Configuration.Install.Installer.Uninstall(System.Collections.IDictionary)
additional_notes.overrides: *content
---

<p>-   If you override the <xref href="System.Configuration.Install.Installer.Install(System.Collections.IDictionary)"></xref> method in a derived class, be sure to call the base class's <xref href="System.Configuration.Install.Installer.Install(System.Collections.IDictionary)"></xref> method first in your derived method. The <xref href="System.Configuration.Install.Installer.Install(System.Collections.IDictionary)"></xref> method calls the <xref href="System.Configuration.Install.Installer.Install(System.Collections.IDictionary)"></xref> method of each installer contained in the <xref href="System.Configuration.Install.Installer.Installers"></xref> property of this instance. After the contained installers run, this method updates the <xref href="System.Collections.IDictionary"></xref> object (specified through the <code>stateSaver</code> parameter) to reflect the status of the installation. The <xref href="System.Collections.IDictionary"></xref> should be empty when passed to the <xref href="System.Configuration.Install.Installer.Install(System.Collections.IDictionary)"></xref> method. If all the <xref href="System.Configuration.Install.Installer.Install(System.Collections.IDictionary)"></xref> methods succeed, the <xref href="System.Configuration.Install.Installer.Commit(System.Collections.IDictionary)"></xref> method is called. Otherwise, the <xref href="System.Configuration.Install.Installer.Rollback(System.Collections.IDictionary)"></xref> method is called.  
  
-   If you need to add installer instances to the <xref href="System.Configuration.Install.Installer.Installers"></xref> collection in the <xref href="System.Configuration.Install.Installer.Install(System.Collections.IDictionary)"></xref> method, be sure to perform the same additions to the collection in the <xref href="System.Configuration.Install.Installer.Uninstall(System.Collections.IDictionary)"></xref> method. However, you can avoid maintaining the collection in both methods if you add installer instances to the <xref href="System.Configuration.Install.Installer.Installers"></xref> collection in the class constructor for your custom installer.</p>

