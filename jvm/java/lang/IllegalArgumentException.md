# IllegalArgumentException

This exception is thrown as a way to indicate that an Illegal valued argument has been passed to a method. This exception also has a few subclasses for similar exceptions, such as NumberFormatException, InvalidPathException and NumberFormatException.

The code ahead is an easy way to reproduce the exception, by trying to create a vector with a negative size.


    Vector<String> myVector = new Vector<String>(-1);

This code would have the following stackstrace:


    Exception in thread "main" java.lang.IllegalArgumentException: Illegal Capacity: -1
        at java.util.Vector.<init>(Vector.java:133)
        at java.util.Vector.<init>(Vector.java:148)
        at IllegalArgumentExample.main(IllegalArgumentExample.java:7)

To avoid this exception, the use of clauses to avoid negative or invalid arguments being passed to methods, specially if the argument comes from external code, is the best solution.

For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/IllegalArgumentException.html) of IllegalArgumentException
