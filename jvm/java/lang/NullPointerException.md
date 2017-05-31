# NullPointerException

NullPointerException is a subclass from RuntimeException. It happens when an applications tries to use an object reference that has the null value. Java allows you to do this since sometimes the object reference has to have a global scope but the value is only acquired inside a scope, as the following example shows:
```java
Boolean test = true;
String str = null;
if(test)
{
    str = "yes";
}
System.out.println(str.length());
```

If the object was declared inside the if, it's reference wouldn't be available for the rest of the code. This creates a new problem though. In the case above, if test = false, then the code tries to access str.length, but str was never initialized, causing a NullPointerException.

Another simple code that throws this exception is the following:
```java
class Obj
{
    public void test()
    {
        //sample code
    }
}
public class NullPointerExample
{
    public static void main(String[] args)
    {
        Obj newObject = null;
        newObject.test();

        public static void main(String[] args)
        {
            Obj newObject = null;
            newObject.test();
        }
    }
}
```

The output in the terminal is:

    Exception in thread "main" java.lang.NullPointerException
        at NullPointerExample.main(NullPointerExample.java:12)


It also happens when
* Trying to access or modify an instance field of an object referred by a null value.
* When reference type is an array type, trying to take the length of a null reference or accessing or modifying the slots of a null reference.
* If the reference type is a subtype of *throwable*, throwing a null reference.

For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/NullPointerException.html) of NullPointerException
