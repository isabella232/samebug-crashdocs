# Exception

This is the superclass of every exception in Java, and it's a subclass of Throwable. *Exception* and all it's subclasses, except for those that are also subclasses of RuntimeException, are *checked exceptions*. This means that they need to be declared in a method or constructor's *throws* clause if the execution of the method or constructor can throw it and propagate outside the method or constructor boundary.

They should be used in cases where the client is supposed to recover from it, and so, they need to be explicitly handled by the code. An example is when using the file libraries on Java:

```java
public class ExceptionExample
{
    private static final String FILENAME = "path";

    public static void main(String[] args)
    {
        BufferedReader br = null;

        try
        {
            br = new BufferedReader(new FileReader(FILENAME));
            //code here to handle file
        }
        catch(FileNotFoundException e)
        {
            e.printStackTrace();
        }
        finally
        {
            try
            {
                br.close();
            } catch (IOException e)
            {
                e.printStackTrace();
            }
        }
    }
}
```

In this case, the StackTrace is printed and shown in the log. But it's possible to not even print it and make the code keep checking for files or just warn the end user that no file was found at that path and go back to other activities.


For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/Exception.html) of Exception.
