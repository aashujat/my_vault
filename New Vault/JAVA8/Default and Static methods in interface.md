## Defualt methods in interface
Methods which are defined inside the interface and tagged with default are known as default methods. These methods are non-abstract methods.

```java
interface Sayable{  
    // Default method   
    default void say(){  
        System.out.println("Hello, this is default method");  
    }  
    // Abstract method  
    void sayMore(String msg);  
}
```
### Reason for introduction of Default methods
In a typical design based on abstractions, where an interface has one or multiple implementations, if one or more methods are added to the interface, all the implementations will be forced to implement them too. Otherwise, the design will just break down.
Default interface methods are an efficient way to deal with this issue. They allow us to add new methods to an interface that are automatically available in the implementations. Therefore, we don't need to modify the implementing classes.
In this way, backward compatibility is neatly preserved without having to refactor the implementers.

**Default methods w.r.t Multiple inheritance** -- There may be a case that a class implements multiple interfaces which have same default methods. so in this scenerio we must have to provide implemetation for that default method otherwise it will give compile timme error due to ambiguity.
```java
interface Left{
default m1(){
System.out.println("Left class implementation");
}
}
interface Right{
default m1(){
System.out.println("Right class implementation");
}
}
class Test implements Left,Right{
//either specify which methods will be calles or provide some new implementation otherwise it will give compile time error
 public void m1(){
//Left.super.m1(); 
// OR
// Right.super.m1();
// OR
System.out.println("Test class implementation");
}
}
```
## Difference between Interface with default methods and Abstract class

### Interface with Default methods
1. Inside interfaces every variable is public,static and final and we cant declare instance variables.
2. Interface never talks about state of object.
3. Inside interface we cant declare constructors.
4. Inside interface we cant declare instance and static blocks.
5. Functional inyerface with default methods can refer lambda expressions.
6. Inside interface we cant override Object class methods.

### Abstract class
1. Inside abstract class we can declare instance variables which are required to the child class.
2. It can talk about state of object.
3. Inside abstract class we can declare constructors.
4. Inside abstract class we can declare instance and static variables.
5. Abstract class cant refer lambda expressions.
6. Inside abstract class we can override Object class methods.

## Static methods inside interface
   
Java 8 also allows us to define and implement static methods in interfaces.Since static methods don't belong to a particular object, they're not part of the API of the 
classes implementing the interface; therefore, they have to be called by using the interface name preceding the method name.

```java
interface Left{
public static void m1(){
System.out.println("Left class static implementation");
}
}
class Test implements Left{
  Test t= new Test();
  t.m1(); // compile time error
Test.m1();  // compile time error
Left.m1(); // correct way to call static method of interface
}
```
**since java 1.8 We can  define main method inside interface and can run interface also. (Similar to class)**
```java
public interface StaticInterface {
	public static void main(String[] args) {
		System.out.println("Static Method inside interface");
	}
}
```
