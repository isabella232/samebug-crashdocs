# ClassCastException

This exception is thrown when trying to make an illegal **downcast** in the code. A downcast is when an object contains a reference to a subtype object and the code casts it to the subtype object. So, for example, the Object below contains a subtype of it, the Integer object, so you can safely downcast it to an Integer so you're able to use Integer's class members.
```java
Object x = 0;
System.out.println((Integer) x);
```

A good example of casting is the below, a HashMap that can hold any kind of datatype you need.

```java
Map<String, Object> multiHashMap = new HashMap<>();

multiHashMap.put("Age", 21);
multiHashMap.put("Name", "Rafael");
multiHashMap.put("Gender", "Male");
multiHashMap.put("HasPassport", true);

Integer Age = (Integer) multiHashMap.get("Age");
String Name = (String) multiHashMap.get("Name");
String Gender = (String) multiHashMap.get("Gender");
Boolean HasPassport = (Boolean) multiHashMap.get("HasPassport");
```

The problem comes when you try to cast to a class that doesn't have the same datatype, such as casting an Object with an Integer to a string.
```java
    Object x = new Integer(0);
    System.out.println((String) x);
```
And the stacktrace would be:  
```
Exception in thread "main" java.lang.ClassCastException: java.lang.Integer cannot be cast to java.lang.String
	at ClassCastExample.main(ClassCastExample.java:9)
```

A simple check is enough to avoid this exception from happening, by using **instanceof** is possible to check if the object in question contains the subtype needed:

```java
if(multiHashMap.get("Age") instanceof Integer)
    Age = (Integer) multiHashMap.get("Age");
```
For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/ClassCastException.html) of ClassCastException.
