---
marp: true
---

# Java Interview Questions
## 1. Why Java is a platform-independent language?

Because the compiler compiles the code and then converts it to platform-independent byte code that can be run on various platforms,For example,You can compile a program in Windows and run it in mac or linux, Java language was created in a way that it is independent of all hardware and software. The installation of a runtime environment (JRE) on the machine is the only prerequisite for running that byte code.


## 2. What is difference between JVM, JRE and JDK ?

+ JVM, or Java Virtual Machine, is an acronym. The byte code is really executed by the virtual machine.
+ Java Runtime Environment is referred to as JRE. It offers a Java runtime environment. It includes JVM, other files, and libraries like rt.jar.
+ Java Development Kit is abbreviated as JDK. It includes JRE plus compilation and debugging tools and is a superset of JRE (javac and java).

## 3. Is java a pure object-oriented programming language?

  No,Beacuse java supports all primitive data types like  byte, boolean, char, short, int, float, long, and double.
  ```java
  int i=10;
  double d=100.0;
  Char c='A';
 System.out.println(i +"\n"+d+"\n"+c);
```

## 4.  Does constructor return any value?

 yes, The constructor implicitly returns the current instance of the class (You can't use an explicit return type with the constructor). 
 ```java
 public Class Skill_lync{
  int marks;
  // Constructor same name as class name,there is no return type
  public skill_lync(){  
     this.marks=0;
  }
 }
 ```

## 5. Is constructor inherited?
No, The constructor is not inherited.
```java
class Parent { 
    public Parent() 
    { 
        System.out.println("ParentClass constructor.");
    } 
 
    public void Display() 
    { 
         System.out.println("ParentClass method.");
    } 
} 
 
public class ChildClass extends SuperClass { 
 
    public static void main(String[] args) 
    { 
        ChildClass object1 = new ChildClass(); // access 
        object1.Display(); // access
        object1.ParentClass(); // not access
        ChildClass object2 = new ParentClass(); // not access 
    } 
}
```

## 6. Can you make a constructor final?
No, the constructor can't be final.

## 7. Can we overload the constructors?
Yes, the constructors can be overloaded by changing the number of arguments accepted by the constructor or by changing the data type of the parameters. Consider the following example.

## 8. What are the differences between the constructors and methods?
+ * A constructor is used to initialize the state of an object.
  * A method is used to expose the behavior of an object.

+ * A constructor must not have a return type.
  * A method must have a return type.

+ * The Java compiler provides a default constructor if you don't have any constructor in a class.
  * The method is not provided by the compiler in any case.

+ * The constructor name must be same as the class name.
  * The method name may or may not be same as class name.

## 9. How many types of constructors are used in Java?
+ ### Default Constructor: 
 Default constructor is the one which does not
accept any value. The default constructor is mainly used to initialize
the instance variable with the default values. It can also be used for
performing some useful task on object creation. A default constructor
is invoked implicitly by the compiler if there is no constructor defined
in the class.
```java 
public class Student{
   int Attendence;
  student(){
      Attendence=1;
  }
}
```
+ ### Parameterized Constructor:
 The parameterized constructor is the
one which can initialize the instance variables with the given values.
In other words, we can say that the constructors which can accept the
arguments are called parameterized constructors.
```java
class Student {
  int p,c;
  //parameterized Constructor created
  public Student(int marks1,marks2){
     this.p=marks1;
     this.c=marks2;
    }
  // Method created display
  public void addMarks(){
   Total=p+c;
   System.out.println("Total Marks Of two subject"+ Total);
  }
  public static void main(String args[]){
  // passing values using object
    student S1=new Student(80,95);
  // method to display 
    S1.addMarks();

  }
}
```

## 10. Can we overload the constructors?
Yes, the constructors can be overloaded by changing the number of
arguments accepted by the constructor or by changing the data type of the
parameters.

## 11. What are the restrictions that are applied to the Java static methods?
Two main restrictions are applied to the static methods.
The static method can not use non-static data member or call the non-static method directly.
this and super cannot be used in static context as they are non-static.
```java
class Parent {
   static void display() {
      System.out.println("Parent class");    
   }
}
public class Child extends Parent {
   void display(){  // trying to override static method 
      System.out.println("Child class");  
   }
   public static void main(String[] args) {
      Parent obj = new Example();
      obj.display();
   }
}
```
## 12. Why is the main method static?
Because the object is not required to call the static method. If we make the main method non-static, JVM will have to create its object first and then call main() method which will lead to the extra memory allocation.

## 13. What are the main uses of this keyword?
There are the following uses of this keyword.

+ this can be used to refer to the current class instance variable.
+ this can be used to invoke current class method (implicitly)
+ this() can be used to invoke the current class constructor.
+ this can be passed as an argument in the method call.
+ this can be passed as an argument in the constructor call.
+ this can be used to return the current class instance from the method.

## 14. Can this keyword be used to refer static members?
Yes, It is possible to use this keyword to refer static members because this is just a reference variable which refers to the current class object. However, as we know that, it is unnecessary to access static variables through objects, therefore, it is not the best practice to use this to refer static members.  
```java
public class Example {
   static int a = 50;
   static int b;
   static void show() {
      System.out.println("Inside the show() method");
      b = a + 5;
   }
   public static void main(String[] args) {
      show();
      System.out.println("The value of a is: " + a);
      System.out.println("The value of b is: " + b);
   }
}
```

## 15. Can we override private methods in java?
can not override a private or static method in Java. If you create a
similar method with same return type and same method arguments in
child class then it will hide the super class method.


## 16. What do you mean by data hiding in java?
Data hiding is the technique of concealing internal data within a class to avoid direct access from outside the class. When we talk about data encapsulation, it conceals both private methods and class data components, whereas data hiding just hides class data components.

## 17. What is the difference between Class and Objects in Java
+ A class defines object properties including a valid range of values, and a
default value. A class also describes object behavior.
+ An object is a member or an "instance" of a class.
An object has a state in which all of its properties have values that you
either explicitly define or that are defined by default settings.
```java
public class car{ // class Created
    int speed;
}
class Main{
  public static void main(String args[]){
    Car c= new car();// Object created
    c.speed;
  }
}
```

## 18. What is Abstraction?
Data abstraction is the process of hiding certain details and showing only
essential information to the user. 
```java
public abstract class helloword{
  // we are inside abstract class;
}
```
## 19. What is Encapsulation?
Encapsulation in Java is the process by which data (variables) and the
code that acts upon them (methods) are integrated as a single unit. By
encapsulating a class's variables, other classes cannot access them, and
only the methods of the class can access them.
```java
public class Addition{
  private int a=10;int b=20; //data members
  private void Sum(){ //data methods()
    int sum=a+b;
    System.out.println("Addition"+sum);
  }
}
```
## 20. What is Polymorphism in java?
Polymorphism refers to the ability of a class to provide different
implementations of a method, depending on the type of object that is
passed to the method. To put it simply, polymorphism in Java allows us to
perform the same action in many different ways.
```java
class Animal {
  public void Sound() {
    System.out.println("The animal makes a sound");
  }
}

class Dog extends Animal {
  public void Sound() {
    System.out.println("The dog says: Bow Bow");
  }
}

class Cat extends Animal {
  public void Sound() {
    System.out.println("The cat says: meow meow");
  }
}
```
## 21. What is Inheritance in java?
Inheritance is a mechanism wherein a new class is derived from an existing
class. In Java, classes may inherit or acquire the properties and methods of
other classes. A class derived from another class is called a subclass,
whereas the class from which a subclass is derived is called a superclass
```java
class Skill_lync{
  //code here
}
 class Learning Extends Skill_lync{
  // code here;
 }
}
```
## 22. What is Constructor in java?
A constructor in Java is a special method that is used to initialize objects.The constructor is called when an object of a class is created.
```java
Class Student{
  public Student(){ //Constructor created

  }
}
```
## 23. Can we declare the static variables and methods in an abstract class?
Yes, we can declare static variables and methods in an abstract method. As we know that there is no requirement to make the object to access the static context, therefore, we can access the static context declared inside the abstract class by using the name of the abstract class.

## 24. Can we have an abstract class without having any abstract method in it?
Yes, we can have an abstract class without Abstract Methods as both
are independent concepts. Declaring a class abstract means that it
can not be instantiated on its own and can only be sub-classed.
Declaring a method abstract means that the Method will be defined in
the subclass.
```java
public abstract class HelloWord{
    static Hi;
  public static void greeting();
}
```

## 25. Difference between Heap and Stack Memory in java?
+ Stack memory is the portion of memory that was assigned to every individual program. And it was fixed. 
+ Heap memory is the portion that was not allocated to the java program but it will be available for use by the java program when it is required, mostly during the runtime of the program.  

## 26. Have you heard about transient variables? When will you use it?
Transient is a variables modifier used in serialization. At the time of
serialization, if we don't want to save the value of a particular variable
in a file, then we use the transient keyword. When JVM comes
across a transient keyword, it ignores the original value of the
variable and saves the default value of that variable data type.

## 27. What are the different types of Strings in java?
+ Mutable Strings
+ Immutable Strings


## 28.  What is object orientation?

It is the perspective towards the real time entities.

## 29. What is the difference between StringBuffer and StringBuilder
StringBuffer vs StringBuilder
+	* StringBuffer is synchronized i.e. thread safe. It means two threads can't call the methods of StringBuffer simultaneously.

     * StringBuilder is non-synchronized i.e. not thread safe. It means two threads can call the methods of StringBuilder simultaneously.

+ *	StringBuffer is less efficient than StringBuilder.	

   *  StringBuilder is more efficient than StringBuffer.

+	* StringBuffer was introduced in Java 1.0	

     *   StringBuilder was introduced in Java 1.5

## 30. What do you understand about Thread Priority?
Every thread when gets born is assigned with a priority value and usually
higher priority gets precedence in execution but it also depends on the
Thread Scheduler implementation which is OS dependent. We can assign
the priority of thread but it doesn’t guarantee that higher priority will get
executed before lower priority thread. Thread priority is an integer value
varies from 1 to 10 where 1 is the lowest and 10 is the highest priority
thread.

## 31. What is the difference between abstract class and an interface?

Abstract class	Interface
+ Abstract class can have abstract and non-abstract methods.	
Interface can have only abstract methods. Since Java 8, it can have default and static methods also.

+ Abstract class doesn't support multiple inheritance.	
Interface supports multiple inheritance.

+ Abstract class can have final, non-final, static and non-static variables.	
Interface has only static and final variables.

+ Abstract class can provide the implementation of interface.	
Interface can't provide the implementation of abstract class.

+ The abstract keyword is used to declare abstract class.	
The interface keyword is used to declare interface.


## 32. What are the rules of inheritance?

1. private members cannot be inherited
2. constructors cannot be inherited
3. Multiple inheritance is not permitted in java
4. Multilevel inheritance is permitted in java
5. Cyclic inheritance is not permitted in java


## 33.  Difference between throw and throws keywords in Java?
The throws keyword is used to declare which exceptions can be
thrown from a method, while the throw keyword is used to explicitly
throw an exception within a method or block of code.
```java
public class ThrowAndThrows  
{  
    
    static void method() throws ArithmeticException  
    {  
        System.out.println("Inside the method()");  
        throw new ArithmeticException("throwing ArithmeticException");  
    }  
    public static void main(String args[])  
    {  
        try  
        {  
            method();  
        }  
        catch(ArithmeticException e)  
        {  
            System.out.println("caught in main() method");  
        }  
    }  
} 
``` 

## 34. Why Strings in java is immutable?
The string is immutable means that we cannot change the object
itself, but we can change the reference to the object. The string is
made final to not allow others to extend it and destroy its
immutability.

## 35.How to stop a thread in java? Explain about sleep () method in a thread?

Answer: We can stop a thread by using the following thread methods:
+ Sleeping
+ Waiting
+ Blocked

## 36. Difference between this() and super() in Java?
The this() in the constructor refers to the current class object. The
super() in the constructor refers immediate parent class object.

## 37. What is volatile in java?
For Java, “volatile” tells the compiler that the value of a variable must
never be cached as its value may change outside of the scope of the
program itself.
## 38.What are two different ways to call a garbage collector?
+ There are 2 ways to call the garbage collector in java.
+ You can use the Runtime. getRuntime(). gc() method- This class
allows the program to interface with the Java Virtual machine. The
“gc()” method allows us to call the garbage collector method.
+ You can also use the System. gc() method which is common.
## 39. How many objects will be created below:
String str1= new String("John");
---
String str2= new String("John");
---
Though we are creating 2 instances, in the memory of String Pool we will
have only one instance of it create with 2 references pointing to it in
Constant Pool
## 40. Can you differentiate between a Checked Exception and an Unchecked exception?
A checked exception is caught at compile time whereas a runtime or
unchecked exception is, as it states, at runtime. A checked exception
must be handled either by re-throwing or with a try-catch block,
whereas an unchecked isn't required to be handled.
## 41.What are memory areas allocated in JVM?
Memory areas allocated in JVM are:
+ Heap area
+ Method area
+ JVM language stacks
+ Program counter (PC) register
+ Native method stacks


## 42.Why main() in java is declared as public static void main? What if the main method is declared as private?
Since the main method in Java is not supposed to return any value, it's made void which simply means main is not returning anything. The main ethod must be declared public, static and void in Java otherwise, JVM will not able to run Java program.

## 43. What is immutable object in java?
The immutable objects are objects whose value can not be changed after
initialization. We can not change anything once the object is created. For
example, primitive objects such as int, long, float, double, all legacy
classes, Wrapper class, String class, etc. In a nutshell, immutable means
unmodified or unchangeable.
## 44. What are access modifier available in java?
Java provides four types of access modifiers or visibility specifiers
i.e. default, public, private, and protected

## 45. What is marker interface?
Marker interfaces are interfaces which have no method but it is used to
indicate JVM to behave specially when any class implement these
interfaces.
For example : If you implement cloneable interface and then call .clone
method of object, it will clone your object. If you do not implement
cloneable interface, it will throw cloneNotSupported exception.

## 46. What is method overloading and method overriding in java?
Method overloading : Method overloading is concept that allows a class
to have same method name but diferent method arguments. Method
overloading is also known as compile time polymorphism.
Method overriding : If child class contain same method as parent class
with same method signature. This is called method overriding. Method
overriding is also known as dynamic polymorphism.

## 47. Can you override static methods in Java?
No, you can not override static methods in Java. You can create same
method in child class but it won’t be dynamic polymorphism. It will be
method hiding. Static methods belong at class level not at object level
hence you can not override static method.

## 48. What is Enum in java?
Java Enum is special data type which represents list of constants values. It
is a special type of java class. It can contain constant, methods and
constructors etc.

## 49. Can we have try without catch block in java?
Yes, we can have try without catch block by using finally block. You can use
try with finally. As you know finally block always executes even if you have
exception or return statement in try block except in case of System.exit().
## 50. What are ways to create a thread in java?
There are two ways to create a thread in java
+ By extending thread class
+ By implementing the Runnable interface.

## 51.Define states of thread in java?
There are 5 states of thread in java
+ New : When you create a thread object and it is not alive yet.
Runnable: When you call start method of thread, it goes into Runnable
+ state. Whether it will execute immediately or execute after some times ,
depends on thread scheduler.
+ Running : When thread is being executed, it goes to running state.
+ Blocked : When thread waits for some resources or some other thread to
complete (due to thread’s join), it goes to blocked state.
+ Dead: When thread’s run method returns, thread goes to dead state.
## 52.Can we call run method directly to start a thread?
No, you can not directly call the run method to start a thread. You need to
call the start method to create a new thread. If you call the run method
directly, it won’t create a new thread and it will be in the same stack as the
main.
## 53. What is garbage Collection?
Garbage Collection is a process of looking at heap memory and deleting
unused object present in heap memory. Garbage Collection frees unused
memory. Garbage Collection is done by JVM.
## 54. What is System.gc()?
This method is used to invoke garbage collection for clean up unreachable
object but it is not guaranteed that when you invoke System.gc() , garbage
collection will definitely trigger.
## 55. What is use of finalize() method in object class?
Finalize method get called when object is being collected by Garbage
Collector. This method can be used to write clean code before object is
collected by Garbage Collector.
## 56. What is difference between final, finally and finalize in Java?
+ final : Final is a keyword which is used with class to avoid being extended,
with instance variable so they can not reassigned, with methods so that
they can not be overridden.
+ finally : Finally is a keyword used with try, catch and finally blocks. Finally
block executes even if there is an exception. It is generally used to do
some clean up work.
+ finalize : Finalize is a method is used to invoke garbage collection for
clean up unreachable object but it is not guaranteed that when you invoke
System.gc(), garbage collection will definitely trigger.
## 57. How do you prevent a class from being sub-classed in Java?
You can prevent a class from being subclassed by using the final
keyword in the class's declaration. Similarly, you can prevent a method
from being overridden by subclasses by declaring it as a final method. An
abstract class can only be subclassed; it cannot be instantiated.
## 58. What is the use of Classloader in Java?
A Java program is made up of a different number of custom classes and
pre-defined classes. When a program is executed, JVM is used to load all
the content of that needed class and through the use of Classloader JVM, it
finds that class.
There are three types of Classloaders:
+  System Class Loader It loads all the classes from the classpath.
+ Extension ClassLoader
It loads all the classes from the extension directory.
+ Bootstrap Class Loader It loads all the pre-defined java classes.
## 59. Which class is a superclass of all classes?
Java.lang.The object is the root class for all the java classes and we don’t
need to extend it. Every other java classes fall back under the object. All
the different non-primitive types including arrays are inherited directly or
indirectly from this class.
## 60. What is the static keyword?
The static keyword is used with a class level variable to make it global so
all the objects will be able to share the same variable. It can also be used
with methods. A static method can access only static variables of the class
and invoke only a static method of the class.
## 61. What is Type casting in Java?
Casting in Java is one of the top topics from where you can get questions
in your interview. When we assign a value of one data type to a different
data type then these two data types might not be compatible with each
other and needs conversion. If data types are compatible with each other
like, in case of the conversion of int value to long then automatic
conversion is done by Java and doesn’t require typecasting. But if data
types are not compatible with each other then they need to be cast for
conversion.
+ Syntax : dataType variablename = (dataType) variableToConvert;
## 62. What is the inner and anonymous inner class?
+ In Java, we can define a class inside a class and they are called
nested classes. Any nested class which is non-static are known as
inner class. Inner classes are associated with objects of the class and
they can access all the variables and methods of the outer class.
+ Any local inner class without any name is known as an anonymous
inner class. It is defined and instantiated in a single statement.
Anonymous inner class always extend a class or implement an
interface. Since an anonymous inner class doesn’t have any name, it
is not possible to create its constructor.
## 63. What is break and continue statement?
+ In a while or do-while loop, we use break for a statement to terminate
the loop. We use a break statement in a switch statement to exit the
switch case. We can also use break statement for terminating the
nested loop.
+ The continue statement is used for skipping the current iteration of a
for, while or do-while loop. We can use the break statement with a
label to skip the current iteration of the outermost loop.
## 64. What is aggregation in Java?
Aggregation is best defined as the entity reference where it represents the
relationship between two classes where the aggregate class contains a
reference to the class which it owns. Aggregation represents a has-a and
whole/part relationship.
## 65. What is the use of System class in Java?
+ Java System class is one of the core classes. One of the easiest
ways to log information for debugging is System.out.print() method.
System class is final so we can’t subclass and override its behavior
through inheritance.
+ System class doesn’t provide any public constructors, so we can’t
instantiate this class and that’s why all of its methods are static.
Some of the utility methods of System class are for array copy, get
the current time, and reading environment variables.
## 66. What is an instanceof keyword?
We can use instanceof keyword in java to check whether an object
belongs to a class or not. We should avoid much usage of it.

## 67. What is Thread Scheduler and Time Slicing?
+ Thread Scheduler is Operating System service which allocates the
CPU time to the available runnable threads. Once a thread is created
and it’s in the runnable phase then its execution depends on the
implementation of the Thread Scheduler.
+ Time Slicing is a process of dividing available CPU time among the
various runnable threads. Allocation of CPU time will depend on the
thread priority or for how much time it is in the waiting state for getting
the CPU time. Thread Scheduling cannot be controlled by Java, so
it’s always better to control it by the application itself.
## 68. Which is more preferred – Synchronized method or Synchronized block?
The synchronized block is more preferred because it doesn’t lock the
object, synchronized methods lock the object and if there are multiple
synchronization blocks in the class, even though they are not related, it will
stop the execution and put them in a wait state to get the lock on the object.

## 69. How to create daemon thread in Java?
Thread class setDaemon(true) is used for creating daemon thread in Java.
We used to call this method before calling the start() method else it will give IllegalThreadStateException.
## 70. What is ThreadLocal?
ThreadLocal in Java is used for creating thread-local variables. We know
that all threads of an object share its variables. So, if the variable is not threaded safe then we can use synchronization. But if we want to avoid
synchronization then we can use ThreadLocal variables.

## 71. What happens when an exception is thrown by the main method?
When an exception is thrown by the main() method, Java Runtime
terminates the program and print the exception message and stack trace in
system console.

## 72. What is an Object in Java?
+ An object in Java is a data structure that represents a real-world
entity. In Java, an object can be a physical object like a car, or it can
be an abstract concept like a mathematical formula.
+ Each object has its own data and behavior. Data is the information
that the object contains, while behavior is the object’s ability to
perform certain actions.
+ Java objects are created using a class. A class is a template that
defines the data and behavior of a particular type of object. Once a
class has been defined, we can create objects of that class by using
the new keyword.

## 73.What if I write static public void instead of public static void?
The program compiles and runs correctly because the order of specifiers
doesn't matter in Java.
## 74. What is the default value of the local variables?
The local variables are not initialized to any default value, neither primitives nor object references.
## 75. What are the advantages of Packages in Java?
+ Packages avoid the name clashes.
+ The Package provides easier access control.
+ We can also have the hidden classes that are not visible outside and
used by the package
+ It is easier to locate the related classes.

## 76. Why is multiple inheritance not supported in java?
To reduce the complexity and simplify the language, multiple inheritance is
not supported in java. Consider a scenario where A, B, and C are three
classes. The C class inherits A and B classes. If A and B classes have the
same method and you call it from child class object, there will be ambiguity
to call the method of A or B class. Since the compile-time errors are better
than runtime errors, Java renders compile-time error if you inherit 2
classes. So whether you have the same method or different, there will be a
compile time error.
## 77. Why does Java not support pointers?
The pointer is a variable that refers to the memory address. They are not
used in Java because they are unsafe(unsecured) and complex to
understand.
## 78. What is object cloning?
The object cloning is used to create the exact copy of an object. The
clone() method of the Object class is used to clone an object.
The java.lang.Cloneable interface must be implemented by the class
whose object clone we want to create. If we don't implement Cloneable
interface, clone() method generates CloneNotSupportedException.
protected Object clone() throws CloneNotSupportedException
## 79. Can we overload the main() method?
Yes, we can have any number of main methods in a Java program by using
method overloading.
## 80. Can we change the scope of the overridden method in the subclass?
Yes, we can change the scope of the overridden method in the subclass.
However, we must notice that we cannot decrease the accessibility of the
method. The following point must be taken care of while changing the
accessibility of the method.
+ The private can be changed to protected, public, or default.
+ The protected can be changed to public or default.
+ The default can be changed to public.
+ The public will always remain public.
## 81. Can you declare the main method as final?
Yes, We can declare the main method as public static final void
main(String[] args){}.
## 82. What is the difference between a compiler and an interpreter?
#### Compiler	
+ A compiler translates the entire source code in a single run.
+ It consumes less time i.e., it is faster than an interpreter.
+ It is more efficient.
+ CPU utilization is more.
+ Both syntactic and semantic errors can be checked simultaneously.
+ The compiler is larger.
+ The compiler is used by the language such as C, C++.
#### Interpreter
+ An interpreter translates the entire source code line by line.
+ It consumes much more time than the compiler i.e., it is slower than the compiler.
+ It is less efficient.
+ CPU utilization is less as compared to the compiler.
+ Only syntactic errors are checked.
+ Interpreters are often smaller than compilers.
+ An interpreter is used by languages such as Java.

## 83. What are the different types of variables in java.


#### INSTANCE Variables:
+ It is a variable which is present inside the class.
+ These variables will get the default values.
Scope of instance variables is inside all the methods and blocks inside the class.
+ Memory is created inside heap segment
+ It is created along with the object.
+ Memory is created each time when the object is created.

#### LOCAL Variables
+ It is a variable which is present inside the method or a block.
+ These variables will not get the default values.
+ Scope of local variables is only inside the method or blocks where they have been initialized.
+ Memory is created inside stack segment
+ It is created when the block or the method is invoked 
+ Memory is created each time when the method is executed.

#### STATIC Variables
+ It is a variable which is present inside the class and is associated with “static” keyword.
+ These variables will get the default values.
+ Scope of static variables is inside all the methods and blocks inside the class.
+ Memory is created inside static segment
+ It is created when the program execution starts.
+ Memory is created only once.
```java
public class WashingMachine{
	    static int water; //Static variables
	     int turn_on=1;   //instance variables
	     int turn_off=0;
	    public void wash(){
	       int Powder=2; //local variables
         int comfort=1;
	       if(turn_on==1){
			      int Add=water+Powder+comfort;
			      System.out.println("Washing cloths");
			  }
		  }
	    public void spin(){
	        System.out.println("spining cloths");
	    }
	     void power_off(){
	     		System.out.println(turn_off+" "+"Take your cloths");
		   }
	    public static void main(String args[]) {
	    	WashingMachine M= new WashingMachine();
	    	M.wash();
	    	M.spin();
	    	M.power_off();
	    }
	}
	
```
## 84. What are the different ways of handling exceptions?

1. try an catch block
2. ducking of exception using throws declaration
3. re-throwing the exception using throw keyword



## 85. What are the different ways to achieve multi-threading in java?

1. Extending the Thread class
2. Implementing the Runnable interface

```java
// By Extend KeyWord
Class MyClass extends Thread{
  void run(){
    //code here
  }
}

//By Runnable inteface
Class MyClass implements Runnable{
 void run(){
  // code here;
 }
}
```

## 86. What is shadowing problem? How do we overcome the shadowing problem?
Shadowing problem refers to a scenario where the complier is under the confusion in identifying the difference between local and instance variables. We can overcome this by making use of "this" keyword.

## 87. how many types of access modifiers is available in Java? 

There are four type of access modifiers in Java:
+ public
+ private 
+ protected
+ package-private (default)


## 88. Difference between public, protected, and private access modifier?  

public is the least restricted while private is the most restricted. This means any class, method or field with public modifier is access to all the classes inside and outside the package on which those classes, methods or fields are declared but in case of private they are only accessible within the class they are declared. 


## 89.What is the default access modifier? What happens if you don't specify access modifier?  

Default access modifier in Java is package level access. This is also known as package private. If you don't specify any modifier then its only visible inside the package. For example following class is only visible to other classes within the same package
```java
package Class;
public class Calculator{

  // your code 

}
```


## 90. What is difference between static and non-static class? 

A nested class can be either static or non-static, in that case its known as Inner class. The difference is that you can access static class without creating instance of top level class but you would need an instance of containing class to access a non-static nested class. 

## 91. Why getter method is better than public variables in Java? 

It provide higher level of abstraction, you can add log statement or return something else like a normalized or calculated value if you want to which cannot be possible if your client is directly accessing the public variable. 

## 92. What is toString()?
A toString() is an in-built method in Java that returns the value given to it in string format. Hence, any object that this method is applied on, will then be returned as a string object.
```java
class HelloWorld {
    public static void main( String args[] ) {

        //Creating an integer of value 10
        Integer number=10;
        // Calling the toString() method as a function of the Integer variable
        System.out.println( number.toString() );
    }
}
```
## 93 What is OutOfMemoryError in Java? How do you deal with that?
The Java virtual machine throws java.lang.OutOfMemoryError when there is not enough memory to run the application e.g. no more memory to create new objects, no more memory to create new threads, etc. The most common OutOfMemoryError is java.lang.OutOfMemoryError: Java heap space, which comes when there is no more memory left to create a new object.

## 94 Can a class implement more than one interface in Java?
Yes, A class can implement more than one interface in Java e.g. A class can be both Comparable and Serializable at the same time. This is why the interface should be the best use for defining Type as described in Effective Java. This feature allows one class to play a polymorphic role in the program.


## 95 What is the difference between Inheritance and Abstraction? 
 Abstraction is an object oriented concept which is used to simply things by abstracting details. It helps in the designing system. On the other hand, Inheritance allows code reuse. You can reuse the functionality you have already coded by using Inheritance.


## 96 Can we make a class both final and abstract at the same time? 
No, you cannot apply both final and abstract keywords to the class at the same time because they are exactly the opposite of each other. A final class in Java cannot be extended and you cannot use an abstract class without extending and making it a concrete class. As per Java specification, the compiler will throw an error if you try to make a class abstract and final at the same time.


## 97 What will happen if you put the System.exit () on the try or catch block? Will finally block execute?
The finally block will always execute even an exception occurred or not but if we put system.exit() in try block then finally block will be executing.
and if any exception is caught and we put System.exit() in catch block then finally block will not executing.
```java
public class Demo {
	
		   public static void main(String[] args) {
		      method();
		   }
		   public static void method() {
		      try {
		    	  int a=10/0;
  		    	  System.exit(0);		    	  
		      } catch(Exception e) {
		         System.out.println(e);
		         System.exit(0);// it won't print finally block
		      }
		      finally {
		         System.out.println("Finally block will execute even after a return statement in a method");
		      }
		   }
		}

```



## 98 What is the difference between the calling start() and run() method of Thread?
 if calling the start() method calls the run() method eventually then why not just call the run() method? Well, the difference is, the start method also starts a new thread. If you call the run method directly then it will run on the same thread, not on a different thread, which is what the original intention would be.


## 99  Why Inheritance is used by Java Programmers? 
Inheritance is utilized for code reuse and utilizing Polymorphism by making a sort order. It's smarter to involve Inheritance for type statement however for code reuse composition is a superior choice since it's more adaptable.


## 100 What is the difference between Polymorphism and Inheritance?
 1. * polymorphism is that which can be defined in multiple forms.
    * Inheritance is one in which a new class is created (derived class) that inherits the features from the already existing class(Base class).	

2. *	it is applied to functions or methods.
   * It is applied to classes. 
3.	*	Polymorphism allows the object to decide which form of the function to implement at compile-time (overloading) as well as run-time (overriding).  
     * Inheritance supports the concept of reusability and reduces code length in object-oriented programming.
4. * it can be compiled-time polymorphism (overload) as well as run-time polymorphism (overriding).	
   * Inheritance can be single, hybrid, multiple, hierarchical and multilevel inheritance.	 
