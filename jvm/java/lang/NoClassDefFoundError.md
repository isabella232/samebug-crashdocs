# NoClassDefFoundError

NoClassDefFoundError, means there's a missing transitive dependency of a .jar file that the code was compiled against. A simple example that throws the exception:

    class Example 
    {
    }

    public class MainExample {
        public static void main(String[] args) {
            Example e = new Example();
        }
    }

This creates two files, Example.class and MainExample.class. If Example.class is deleted, for example, the following exception will be thrown:

	Exception in thread "main" java.lang.NoClassDefFoundError: Example
		at MainExample.main(MainExample.java:13)
		at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
		at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
		at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
		at java.lang.reflect.Method.invoke(Method.java:498)
		at com.intellij.rt.execution.application.AppMain.main(AppMain.java:147)
	Caused by: java.lang.ClassNotFoundException: Example
		at java.net.URLClassLoader.findClass(URLClassLoader.java:381)
		at java.lang.ClassLoader.loadClass(ClassLoader.java:424)
		at sun.misc.Launcher$AppClassLoader.loadClass(Launcher.java:331)
		at java.lang.ClassLoader.loadClass(ClassLoader.java:357)
		... 6 more
		
This happens when there's a library or framework being used and it "depends" on external code to work, or if there's missing class or jar files. All the .class files need to be in the right .jar files, and the .jar files inside their correct folders and inside the Class-Path. The use of a building tool (such as Maven or Gradle) is recommended to help with this problem. Some libraries (such as com.fasterxml) require external dependencies, and if they're not in the dependencies (pom.xml) or in your Class-path, this exception will be thrown.

There's also a ClassNotFoundException being thrown, and that's the cause of the error.

Changes