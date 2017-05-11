---
summary: Returns true if the specified Principal is a member of the PrincipalCollection, false otherwise.  The Principal can be specified in the same manner as in the <xref href="System.DirectoryServices.AccountManagement.PrincipalCollection.Add*"></xref>.methods.
remarks: As with <xref:System.DirectoryServices.AccountManagement.PrincipalCollection.Add%2A>, and <xref:System.DirectoryServices.AccountManagement.PrincipalCollection.Remove%2A> there are four overloads to this function, but they all do the same thing.  The extra overloads are only implemented to improve usability, so that developers using Intellisense see overloads that take a <xref:System.DirectoryServices.AccountManagement.UserPrincipal>, <xref:System.DirectoryServices.AccountManagement.GroupPrincipal>, or <xref:System.DirectoryServices.AccountManagement.ComputerPrincipal> object.  Calling any one of the User, Group, or Computer overloads is exactly equivalent to calling the <xref:System.DirectoryServices.AccountManagement.Principal> overload.
uid: System.DirectoryServices.AccountManagement.PrincipalCollection.Contains*
---