---
summary: Starts the listener for receiving dependency change notifications.
remarks: "The <xref:System.Data.SqlClient.SqlDependency> listener will restart when an error occurs in the [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)] connection.  \n  \n Multiple calls to the <xref:System.Data.SqlClient.SqlDependency.Start%2A> method can be made, subject to the following restrictions:  \n  \n-   Multiple calls with identical parameters (the same connection string and Windows credentials in the calling thread) are valid.  \n  \n-   Multiple calls with different connection strings are valid as long as:  \n  \n    -   Each connection string specifies a different database, or  \n  \n    -   Each connection string specifies a different user, or  \n  \n    -   The calls come from different application domains.  \n  \n You can make the <xref:System.Data.SqlClient.SqlDependency> work correctly for applications that use multiple threads to represent different user credentials without giving the dbo role to the group, because different users can subscribe and listen (using <xref:System.Web.Caching.SqlCacheDependency> or <xref:System.Data.SqlClient.SqlCommand>) to a notification queue created by an administrator. When the relevant application domain starts, call Start with the (Windows) credentials of a user that has permission to initialize a service/queue (the CREATE QUEUE and CREATE SERVICE permissions for the database). Ensure that Start is only called once per AppDomain, otherwise an ambiguity exception is raised.  The user thread must have permission to subscribe to the notification (the SUBSCRIBE QUERY NOTIFICATIONS permission for the database). <xref:System.Data.SqlClient.SqlDependency> will associate the subscription request of a non-administrator user to the service/queue created by the administrator."
uid: System.Data.SqlClient.SqlDependency.Start*
---