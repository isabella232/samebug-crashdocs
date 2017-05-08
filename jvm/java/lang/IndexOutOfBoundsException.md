# IndexOutOfBoundsException

This exception is thrown to indicate that  an index that’s being passed to an object or method is out of range. For an array, for example, this means that the index passed is either negative or bigger than the size of it.
One of the common causes in java is the thought that Java is 1-indexed, meaning that the first index is 1, but in Java, the first index is 0, this means the following code, that uses an index to access elements of an string, would throw the exception:

    public class StringExample{
        public static void main(String[] args){
            String word = "Word";
            for(int i = 1; i <= word.length(); i++){
                System.out.print(word.charAt(i));
            }
        }
    }

As expected, this code outputs the letters "ord", since the 'W' is stored in word[0] and throws the following exception:

    Exception in thread "main" java.lang.IndexOutOfBoundsException: String index out of range: 4
        at java.lang.String.charAt(String.java:658)
	    at StringExample.main(StringExample.java:8)

# ArrayOutOfBoundsException

ArrayOutOfBoundsException is a subclass from IndexOutOfBoundsException, so similarly, is thrown when trying to use an out of range index.

    Int[] numbers = new int[6];

    for(int i = 1; i <= numbers.length; i++)
    {
        System.out.println(numbers[i]);
    }

The program would be missing the first term numbers[0] and trying to access an inexistent term numbers[6], which would cause the exception java.lang.ArrayIndexOutOfBoundsException to be thrown. This exceptions is also thrown by some other classes, such as ArrayList.

The code ahead throws the exception:



The first index for strings is also 0, so the code above would throw java.lang.IndexOutOfBoundsException.

# ArrayOutOfBoundsException
