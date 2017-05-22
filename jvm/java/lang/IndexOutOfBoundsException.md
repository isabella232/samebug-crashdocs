# IndexOutOfBoundsException

This exception is thrown to indicate that  an index that’s being passed to an object or method is out of range. It has a few subclasses for similar problems, such as ArrayIndexOutOfBoundsException and StringIndexOutOfBoundsException. For an array, for example, this means that the index passed is either negative or bigger than the size of it.

One of the common causes in java is the thought that Java is 1-indexed, meaning that the first index is 1, but in Java, the first index is 0, this means the following code, that uses an index to access elements of an string, would throw StringIndexOutOfBoundsException, one of the subclasses of IndexOutOfBoundsException.

    public class StringExample
    {
        public static void main(String[] args)
        {
            String word = "Word";
            for(int i = 1; i <= word.length(); i++)
                System.out.print(word.charAt(i));

        }
    }

Here's the output in the terminal:

    ord
    Exception in thread "main" java.lang.IndexOutOfBoundsException: String index out of range: 4
        at java.lang.String.charAt(String.java:658)
	    at StringExample.main(StringExample.java:8)

Since the indexes start at 0, the code skipped the first letter and tried to access word.charAt(4), throwing the exception.

For more information, here is the [Javadoc](http://docs.oracle.com/javase/7/docs/api/java/lang/IndexOutOfBoundsException.html) of IndexOutOfBoundsException
