# RuntimeException

RuntimeException is the superclass of every exception that can be thrown during normal operation of the Java Virtual Machine. It's also a subclass of the Exception class. This class, and all it's subclasses are *unchecked exceptions*, meaning that they don't need to be specified in the method's constructor or in the throw clause of it, differently from it's superclass and it's subclasses, that are *checked exceptions*. Normally, RuntimeExceptions indicate programming errors.

Essentialy, any exception that doesn't have to be explicitly handled by the code, such as ArrayIndexOutOfBoundsException, NumberFormatException, NullPointerException, and that most times, would be avoided by a simple check (such as checking if the index is negative or bigger than the size of the array, if the value being passed to a method is null, etc).

This exception, besides being the superclass of other RuntimeExceptions, is also thrown explicitly by 3rd party code and user-made code, mostly with the intention of creating a fast exception without giving all the details to it.

According to Oracle, if a client is expected to handle and to recover from an exception, it should be a checked exception(of type Exception). One example is when trying to open files: an IDE will tell the user that he has to handle a FileNotFoundException when using the file handling classes of Java. Otherwise, if the client can do nothing to recover from it, it should be unchecked (of type RuntimeException).

To declare a custom RuntimeException:
```java
public class NameOfYourExceptionHere extends RuntimeException
{
    //here is possible to override methods that need different handling from the standard ones in RuntimeException.
}
```

For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/RuntimeException.html) of RuntimeException.
