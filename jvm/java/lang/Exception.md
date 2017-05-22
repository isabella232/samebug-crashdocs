# Exception

This is the superclass of every exception in Java, and it's a subclass of Throwable. *Exception* and all it's subclasses, except for those that are also subclasses of RuntimeException, are *checked exceptions*. This means that they need to be declared in a method or constructor's *throws* if the execution of the method or constructor can throw it and propagate outside the method or constructor boundary.

For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/Exception.html) of Exception. 
