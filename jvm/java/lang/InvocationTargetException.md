# InvocationTargetException

This is a *checked* exception, and it is thrown when using invoked methods or constructors through Java Reflection.

It's used when an invoked method or constructor throws an exception, and it serves as a wrap for this exception, so the user is able to differentiate between an exception caused by the method or an exception caused by reflection call. To access the "target exception" there's the getTargetException() method, as well as the Throwable.getCause() method. If the method being invoked requires any exception handling of it's own, the user has to do it as well.

An example below:
```java
public Socket createRFSocket(int channel) throws Exception
{
    if(_createRFSocket == null)
    {
        try
        {
            return(Socket)_createRFSocket.invoke(mDevice, channel);
        }
        catch(InvocationTargetException x)
        {
            if(x.getCause() intansceof Exception)
                throw (Exception) x.getCause();
            else
                throw ite;
        }
    }
}
```

This code allows to check if the exception has another exception in the wrap, meaning it'd be an exception thrown by the method being invoked. Otherwise, it just throws a normal InvocationTargetException. If the method being called required for an IOException handling for example, there need to be another catch that handles that exception.

```java
try{exampleMethod.invoke(null,exampleParam);}

catch(InvocationTargetException ite)
{
    try{throw ite.getCause();}
    catch(IOException e)
    {
    }
}
```

For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/reflect/InvocationTargetException.html) of InvocationTargetException.
