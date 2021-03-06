# Why Does this Library Exist?

When MyBatis Generator (originally called "Abator") was first created in 2005, MyBatis3 didn't exist yet so the generator only generated code for iBatis. MyBatis generator delivered a "query by example" functionality with the very first release of MyBatis generator, and I believe this capability is in wide use.  Unfortunately iBatis had a very limited ability to generate dynamic SQL with only a few custom XML tags.  So the "by example" code generated by MyBatis generator has the following limitations:

1. It is large and complex
2. It has very limited capabilities (coding mixed AND and OR expressions in WHERE clauses is very difficult)
3. It is hard to extend

When MyBatis came along it had much more advanced capabilities for dynamic SQL generation, but MyBatis Generator simply duplicated the existing functionality in the "by example" classes.  This was a good thing in that it preserved some compatibility when moving from iBatis to MyBatis, but it also retained all the negative aspects of the generated code.

In late 2016, I began thinking about a new and improved version of MyBatis generator.  I had these general goals in mind:

1. Greatly increase the capabilities of the generated code - especially by supporting arbitrarily complex WHERE clauses, JOINS, aggregate functions, etc.
2. Improve the ability to extend the generated code
3. Reduce the size and complexity of the generated code
4. Use a cleaner coding style than MyBatis generator, and employ all the advances in the Java language - especially the pseudo functional style from Java 8

In order to accomplish these goals, I accepted the following:

1. The new code would not be compatible with prior code
2. The new code would require Java 8 or better to run
3. The new code would have a permanent dependence on a utility library (this library) to implement its vastly improved capabilities

My initial work was in implementing an arbitrarily complex WHERE clause.  As work progressed it became clear that this library could do much more than just generate a WHERE clause.  So now the library implements a substantial portion of the standard SQL DELETE, INSERT, SELECT, and UPDATE statements and supports both MyBatis and Spring JDBC templates.

This library stands alone and does not require the use of MyBatis Generator.  Ultimately MyBatis Generator will be updated so that it will generate code for this library, but the generated code will be much smaller (in fact, very much smaller).

I hope you find this library useful, and that the added capabilities are worth the loss of backward compatibility with prior versions of code generated by MyBatis Generator.

Jeff Butler<br/>
November 2017
