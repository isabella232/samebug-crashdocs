# ArrayIndexOutOfBoundsException

ArrayIndexOutOfBoundsException is a subclass from IndexOutOfBoundsException, so similarly, is thrown when trying to use an out of range index.

The code above is a simple way to throw the exception:

    Int[] numbers = {1,2,3,4,5,6};

    for(int i = 1; i <= numbers.length; i++)
    {
        System.out.println(numbers[i]);
    }

The output in the terminal would be:

    23456
    Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 6
        at ArrayExample.main(ArrayExample.java:11)

It's missing the first number in the array and trying to access numbers[6], since in Java, indexes start at 0.

For more information, here is the [Javadoc](http://docs.oracle.com/javase/7/docs/api/java/lang/ArrayIndexOutOfBoundsException.html?is-external=true) of ArrayIndexOutOfBoundsException.
