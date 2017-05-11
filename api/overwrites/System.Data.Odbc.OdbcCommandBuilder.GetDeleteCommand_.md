---
summary: Gets the automatically generated <xref href="System.Data.Odbc.OdbcCommand"></xref> object required to perform deletions at the data source.
remarks: "You can use the <xref:System.Data.Odbc.OdbcCommandBuilder.GetDeleteCommand%2A> method for informational or troubleshooting purposes because it returns the <xref:System.Data.Odbc.OdbcCommand> object to be executed.  \n  \n You can also use <xref:System.Data.Odbc.OdbcCommandBuilder.GetDeleteCommand%2A> as the basis of a modified command. For example, you might call <xref:System.Data.Odbc.OdbcCommandBuilder.GetDeleteCommand%2A> and modify the <xref:System.Data.Odbc.OdbcCommand.CommandTimeout%2A> value, and then explicitly set that on the <xref:System.Data.Odbc.OdbcDataAdapter>.  \n  \n After the SQL statement is first generated, you must explicitly call <xref:System.Data.Common.DbCommandBuilder.RefreshSchema%2A> if it changes the statement in any way. Otherwise, the <xref:System.Data.Odbc.OdbcCommandBuilder.GetDeleteCommand%2A> still will be using information from the previous statement, which might not be correct. The SQL statements are first generated when the application calls either <xref:System.Data.Common.DbDataAdapter.Update%2A> or <xref:System.Data.Odbc.OdbcCommandBuilder.GetDeleteCommand%2A>."
uid: System.Data.Odbc.OdbcCommandBuilder.GetDeleteCommand*
---