# InvocationTargetException

This is a *checked* exception, and it is thrown when using invoked methods or constructors through Java Reflection.

It's used when an invoked method or constructor throws an exception, and it serves as a wrap for this exception, so the user is able to differentiate between an exception caused by the method or an exception caused by refletction call. To access the "target exception" there's the getTargetException() method, as well as the Throwable.getCause() method.

For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/reflect/InvocationTargetException.html) of InvocationTargetException.
