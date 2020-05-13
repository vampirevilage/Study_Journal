---
layout: post
title: Throwables in Java
date: 2020-05-10 15:40:00 +0530
description: let's find out the secret behind Errors, Exceptions and Throwables in Java and its Hierarchy.
img: /codingimgs/LRU-cache-implementation.jpg
tags: [Throwable, Java, Coding]
author: Chetan Chauhan
---
# Throwables in Java
The Throwable class is the superclass of all errors and exceptions in the Java language. Only objects that are instances of this class (or of one of its subclasses) are thrown by the Java Virtual Machine or can be thrown by the Java throw statement. Similarly, only this class or one of its subclasses can be the argument type in a catch clause.

A Throwable class contains a snapshot of the execution stack of its thread at the time it was created. It can also contain a message string that gives more information about the error.

Following is the declaration for [**java.lang.Throwable**](https://docs.oracle.com/javase/7/docs/api/java/lang/Throwable.html) class −
```java
public class Throwable
   extends Object
      implements Serializable
```
<br><br>
This class inherits methods from [**java.lang.Object**](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html) ::
- protected Object clone()
- boolean equals(Object obj)
- protected void finalize()
- Class<?> getClass()
- int hashCode()
- void notify()
- void notifyAll()
- String toString()
- void wait()
- void wait(long timeout)
- void wait(long timeout, int nanos)
<br><br>

Let's see some **Constructors** for Throwable class::

|Sr. No. | Constructor | Description |
|--------|----------|----------|
|1. | Throwable() | This constructs a new throwable with null as its detail message. |
|2. | Throwable(String message) | This constructs a new throwable with the specified detail message. |
|3. | Throwable(String message, Throwable cause) | This constructs a new throwable with the specified detail message and cause. |
|4. | Throwable(Throwable cause) | This constructs a new throwable with the specified cause and a detail message of (cause==null ? null : cause.toString()) (which typically contains the class and detail message of cause). |
||||
<br><br>
And now let's explore the class methods ::


|Sr. No. | Method | Description |
|--------|----------|----------|
|1. | Throwable fillInStackTrace() | This method fills in the execution stack trace. |
|2. | Throwable getCause() | This method returns the cause of this throwable or null if the cause is nonexistent or unknown. |
|3. | String getLocalizedMessage() | This method creates a localized description of this throwable. Subclasses may override this method in order to produce a locale-specific message. For subclasses that do not override this method, the default implementation returns the same result as getMessage().|
|4. | String getMessage() | This method returns the detail message string of this throwable. |
|5. | StackTraceElement[] getStackTrace() | This method provides programmatic access to the stack trace information printed by printStackTrace(). |
|6. | Throwable initCause(Throwable cause) | This method initializes the cause of this throwable to the specified value. |
|7. | void printStackTrace() | This method prints this throwable and its backtrace to the standard error stream. |
|8. | void printStackTrace(PrintStream s) | This method prints this throwable and its backtrace to the specified print stream. |
|9. | void printStackTrace(PrintWriter s) | This method prints this throwable and its backtrace to the specified print writer. |
|10. | void setStackTrace(StackTraceElement[] stackTrace) | This method sets the stack trace elements that will be returned by getStackTrace() and printed by printStackTrace() and related methods. |
|11. | String toString() | This method returns a short description of this throwable. |
<br><br>
Okay, that was too much of methods and constructors, but this is the basic which is common to all *Throwables*. Further moving on, we will see the heirarchy of Throwable class but before that some basics on Throwable::

A *Throwable* instance contains the current execution stack, captured when the error exception occurred. It can also contain a message (obtained via the *getMessage()* method), indicating the relevant error message. Lastly, for exception chains where one error causes another error to be thrown, a *Throwable* can obtain a potential cause (collected via the *getCause()* method) as well.

Let's dive into the hierarchy now ::
Throwable class is extended by two classes :
- Exception
- Error

<br><br>
Let's see the hierarchy ::
- Throwable
    - Error
        - AssertionError
        - LinkageError
            - BootstrapMethodError
            - ClassCircularityError
            - ClssFormatError
                - UnsupportedClassVersionError
            - ExceptionInInitializerError
            - IncompatibleClassChangeError
                - AbstractMethodError
                - IllegalAccessError
                - InstantiationError
                - NoSuchFieldError
                - NoSuchMethodError
            - NoClassDefFoundError
            - UnsatisfiedLinkError
            - VerifyError
        - ThreadDeath
        - VirtualMachineError
            - InternalError
            - OutOfMemoryError
            - StackOverflowError
            - UnknownError
    - Exception
        - CloneNotSupportedException
        - InterruptedException
        - IOException
            - FileNotFoundException
            - SocketException
                - ConnectException
            - UnknownHostException
        - ReflectiveOperationException
            - ClassNotFoundException
            - IllegalAccessException
            - InstantiationException
            - InvocationTargetException
            - NoSuchFieldException
            - NoSuchMethodException
        - RuntimeException
            - ArithmeticException
            - ArrayStoreException
            - ClassCastException
            - ConcurrentModificationException
            - EnumConstantNotPresentException
            - IllegalArgumentException
                - IllegalThreadStateException
                - NumberFormatException
            - IllegalMonitorStateException
            - IllegalStateException
            - IndexOutOfBoundsException
                - ArrayIndexOutOfBoundsException
                - StringIndexOutOfBoundsException
            - NegativeArraySizeException
            - NullPointerException
            - SecurityException
            - TypeNotPresentException
            - UnsupportedOperationException
<br><br>

I wish I could show the hierarchy more visibly but this is the most creative idea that came to my mind. Lets see it in visual format.

<img src="{{site.baseurl}}/assets/img/codingimgs/Throwable_Error_Hierarchy.gif" alt="Error Hierarchy"
	title="Error Hierarchy" width="80%" height="80%" />

<img src="{{site.baseurl}}/assets/img/codingimgs/Throwable_Exception_Hierarchy.gif" alt="Exception Hierarchy"
	title="Exception Hierarchy" width="80%" height="80%" />

