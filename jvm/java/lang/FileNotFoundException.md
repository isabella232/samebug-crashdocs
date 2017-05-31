# FileNotFoundException

This exception is thrown by the constructors of Java's file handling classes. It is thrown when the file specified in the pathname given to these objects either doesn't exist or it's not accessible for some reason.

A few situations may also throw this exception, for example:

* Opening a read-only file with writing privileges
* Path is broken
* File is in the wrong directory
* Wrong file extension.
* Sometimes, if known file extensions are set to be hidden, there might be a file named "text.txt.txt", but in file browser it'd look like "text.txt".
* File handling requires exception handling in Java, either in a try-catch or with a "throws" in the method or constructor name.

An IDE would complain about the last case, but in cases where no IDE is being used, the same exception would be thrown.

A simple try-catch block to handle a FileNotFoundException is below:
```java
public class FileNotFoundExample
{
    final String filename = "yourpath";
    public static void main(String[] args)
    {
        FileReader fr = null;

        try
        {
            fr = new FileReader(filename);
        }
        catch(FileNotFoundException e)
        {
            e.printStackTrace();
        }
    }
}
```

If avoiding this exception is needed, including checks such as file.canRead() and file.exists() might help, as shown below:
```java
public static void main(String[] args) throws FileNotFoundException
{
    File file = new File("text.txt");
    if(file.exists() && file.canRead())
    {
        //example code
    }
}
```



For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/io/FileNotFoundException.html) of FileNotFoundException.
