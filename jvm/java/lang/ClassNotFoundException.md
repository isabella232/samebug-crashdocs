# ClassNotFoundException

ClassNotFoundException, as the name suggests, means Java could not find a class that it's being used in the program. This exception is thrown by some methods such as Class.forName(), loadClass() and findSystemClass(), and normally indicates that there's a problem with the classpath or a missing class. Below, a simple way to throw this exception:

    public class MainClass {
        public static void main(String[] args) {
            try {
                Class.forName("com.fasterxml.jackson.core");
            } catch(ClassNotFoundException e) {
                e.printStackTrace();
            }
        }
    }


Below, the output of the terminal:


    java.lang.ClassNotFoundException: com.fasterxml.jackson.core
    	at java.net.URLClassLoader.findClass(URLClassLoader.java:381)
    	at java.lang.ClassLoader.loadClass(ClassLoader.java:424)
    	at sun.misc.Launcher$AppClassLoader.loadClass(Launcher.java:331)
    	at java.lang.ClassLoader.loadClass(ClassLoader.java:357)
    	at java.lang.Class.forName0(Native Method)
    	at java.lang.Class.forName(Class.java:264)
    	at MainClass.main(MainClass.java:10)
    	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
    	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
    	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
    	at java.lang.reflect.Method.invoke(Method.java:498)
    	at com.intellij.rt.execution.application.AppMain.main(AppMain.java:147)

This exception happens in many different scenarios, but the most common cause is a broken Class-Path, caused by either missing files or maybe even a change in disk layout which could possibly break the Class-Path. Java looks for all the folders and subfolders in the Class-Path to find the classes. Most common solutions include:

* If the code is running from the command line, the argument sent with -cp (Class-Path) might be wrong.
* The Class-Path entry in MANIFEST.MF might be wrong.
* In some IDEs (such as intelliJ and Eclipse) there's a field where you can set the Classpath for the project, and it could be wrong.
* There might be misplaced JAR files.
* There might be missing or mistyped dependencies in the build tool.

For more information, here is the [Javadoc](https://docs.oracle.com/javase/7/docs/api/java/lang/ClassNotFoundException.html) of ClassNotFoundException
