---
summary: Returns a string array that contains the substrings in this instance that are delimited by elements of a specified string or Unicode character array.
remarks: "<xref:System.String.Split%2A> is used to break a delimited string into substrings. You can use either a character array to specify zero, one, or multiple delimiting characters (the <xref:System.String.Split%28System.Char%5B%5D%29> method), or you can use a character array to specify zero, one, or multiple delimiting strings. Overloads of the <xref:System.String.Split%2A> method allow you to limit the number of substrings returned by the method (the <xref:System.String.Split%28System.Char%5B%5D%2CSystem.Int32%29> method), to determine whether empty strings are included in the returned substrings (the <xref:System.String.Split%28System.Char%5B%5D%2CSystem.StringSplitOptions%29> and <xref:System.String.Split%28System.String%5B%5D%2CSystem.StringSplitOptions%29> methods, or to do both (the <xref:System.String.Split%28System.Char%5B%5D%2CSystem.Int32%2CSystem.StringSplitOptions%29> and <xref:System.String.Split%28System.String%5B%5D%2CSystem.Int32%2CSystem.StringSplitOptions%29> methods).  \n  \n> [!IMPORTANT]\n>  For more detailed information on the <xref:System.String.Split%2A> method, as well as for examples that call each overload, see the documentation for the individual overloads of <xref:System.String.Split%2A>.  \n  \n The <xref:System.String.Split%2A> method is not always the best way to break a delimited string into substrings. If you don't want to extract all of the substrings of a delimited string, or if you want to parse a string based on a pattern instead of a set of delimiter characters, consider the following alternatives.  \n  \n## Regular expressions  \n If your strings conform to a fixed pattern, you can use a regular expression to extract and handle their elements. For example, if strings take the form \"*number* *operand* *number*\" you can use a [regular expression](~/docs/standard/base-types/regular-expressions.md) to extract and handle the string's elements. Here's an example:  \n  \n [!code-csharp[System.String.Split#8](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.String.Split/cs/splitalt1.cs#8)]\n [!code-vb[System.String.Split#8](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.Split/vb/splitalt1.vb#8)]  \n  \n The regular expression pattern `(\\d+)\\s+([-+*/])\\s+(\\d+)` is defined like this:  \n  \n|Pattern|Description|  \n|-------------|-----------------|  \n|`(\\d+)`|Match one or more decimal digits. This is the first capturing group.|  \n|`\\s+`|Match one or more whitespace characters.|  \n|`([-+*/])`|Match an arithmetic operator sign (+, -, *, or /). This is the second capturing group.|  \n|`\\s+`|Match one or more whitespace characters.|  \n|`(\\d+)`|Match one or more decimal digits. This is the third capturing group.|  \n  \n You can also use a regular expression to extract substrings from a string based on a pattern rather than a fixed set of characters. This is a common scenario when either of these conditions occurs:  \n  \n-   One or more of the delimiter characters does not always serve as a delimiter in the <xref:System.String> instance.  \n  \n-   The sequence and number of delimiter characters is variable or unknown.  \n  \n For example, the <xref:System.String.Split%2A> method cannot be used to split the following string, because the number of `\\n` (in C#) or `vbCrLf` (in Visual Basic) characters is variable, and they do not always serve as delimiters.  \n  \n```  \n  \n[This is captured\\ntext.]\\n\\n[\\n[This is more captured text.]\\n]  \n\\n[Some more captured text:\\n   Option1\\n   Option2][Terse text.]  \n  \n```  \n  \n A regular expression can split this string easily, as the following example shows.  \n  \n [!code-csharp[System.String.Split#9](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.String.Split/cs/splitalt2.cs#9)]\n [!code-vb[System.String.Split#9](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.Split/vb/splitalt2.vb#9)]  \n  \n The regular expression pattern `\\[([^\\[\\]]+)\\]` is defined like this:  \n  \n|Pattern|Description|  \n|-------------|-----------------|  \n|`\\[`|Match an opening bracket.|  \n|`([^\\[\\]]+)`|Match any character that is not an opening or a closing bracket one or more times. This is the first capturing group.|  \n|`\\]`|Match a closing bracket.|  \n  \n The <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=fullName> method is almost identical to <xref:System.String.Split%2A?displayProperty=fullName>, except that it splits a string based on a regular expression pattern instead of a fixed character set. For example, the following example uses the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=fullName> method to split a string that contains substrings delimited by various combinations of hyphens and other characters.  \n  \n [!code-csharp[System.String.Split#10](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.String.Split/cs/splitalt3.cs#10)]\n [!code-vb[System.String.Split#10](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.Split/vb/splitalt3.vb#10)]  \n  \n The regular expression pattern `\\s-\\s?[+*]?\\s?-\\s` is defined like this:  \n  \n|Pattern|Description|  \n|-------------|-----------------|  \n|`\\s-`|Match a whitespace character followed by a hyphen.|  \n|`\\s?`|Match zero or one whitespace character.|  \n|`[+*]?`|Match zero or one occurrence of either the + or * character.|  \n|`\\s?`|Match zero or one whitespace character.|  \n|`-\\s`|Match a hyphen followed by a whitespace character.|  \n  \n## Search methods and the Substring method  \n If you aren't interested in all of the substrings in a string, you might prefer to work with one of the string comparison methods that returns the index at which the match begins. You can then call the <xref:System.String.Substring%2A> method to extract the substring that you want. The string comparison methods include:  \n  \n-   <xref:System.String.IndexOf%2A>, which returns the zero-based index of the first occurrence of a character or string in a string instance.  \n  \n-   <xref:System.String.IndexOfAny%2A>, which returns the zero-based index in the current string instance of the first occurrence of any character in a character array.  \n  \n-   <xref:System.String.LastIndexOf%2A>, which returns the zero-based index of the last occurrence of a character or string in a string instance.  \n  \n-   <xref:System.String.LastIndexOfAny%2A>, which returns a zero-based index in the current string instance of the last occurrence of any character in a character array.  \n  \n The following example uses the <xref:System.String.IndexOf%2A> method to find the periods in a string. It then uses the <xref:System.String.Substring%2A> method to return full sentences.  \n  \n [!code-csharp[System.String.Split#11](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.String.Split/cs/splitalt4.cs#11)]\n [!code-vb[System.String.Split#11](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.Split/vb/splitalt4.vb#11)]"
uid: System.String.Split*
---