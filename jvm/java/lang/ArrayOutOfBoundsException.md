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
