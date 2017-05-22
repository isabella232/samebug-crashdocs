# IllegalArgumentException

This exception is thrown as a way to indicate that an Illegal valued argument has been passed to a method. This exception also has a few subclasses for similar exceptions, such as NumberFormatException, InvalidPathException and NumberFormatException.

The code ahead is an easy way to reproduce the exception, by trying to create a vector with a negative size.


    Vector<String> myVector = new Vector<String>(-1);

This code throws the following exception


    Exception in thread "main" java.lang.IllegalArgumentException: Illegal Capacity: -1
        at java.util.Vector.<init>(Vector.java:133)
        at java.util.Vector.<init>(Vector.java:148)
        at IllegalArgumentExample.main(IllegalArgumentExample.java:7)

To fix this, try to check for negatives and illegal values before passing them to a method.
