# NumberFormatException

This exception is one of the most common exceptions in Java, and it happens when you're trying to convert a String into a numeric value but the string is not properly formatted for doing so.

An example is the following code:
```java
public class StringToInt
{
    public static void main()
    {
        try
        {
            String s = "testword";
            int i = Integer.parseInt(s);
            System.out.println("The value is equal to: " + i);
        }
        catch(NumberFormatException nfe)
        {
            nfe.printStackTrace();
        }
    }
}
```
And it would have the following stacktrace:

    java.lang.NumberFormatException: For input string: "testword"
        at java.lang.NumberFormatException.forInputString(NumberFormatException.java:48)
        at java.lang.Integer.parseInt(Integer.java:447)
        at java.lang.Integer.parseInt(Integer.java:497)
        at com.devdaily.javasamples.NumberFormatExample.main(NumberFormatExample.java:11)

One good way to avoid this exception is parsing through the string to check for integers before passing it to another method, specially if the string comes from external code.

For more information, here's the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/NumberFormatException.html) of NumberFormatException.
