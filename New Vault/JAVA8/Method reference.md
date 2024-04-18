# Method Reference
Method reference is used to refer method of functional interface. It is compact and easy form of lambda expression. 
Each time when you are using lambda expression to just referring a method, you can replace your lambda expression 
with method reference.

1. Reference to a static method.
2. Reference to an instance method.
3. Reference to a constructor. 

## Reference to a static method
 You can refer to static method defined in the class.
 ```java
   ContainingClass::staticMethodName
```
### without method reference
```java
interface Interf{
public void m1();
}
class Test{
public static void main(String [] args){
Interf i= () ->{
System.out.println("interface implementation without Method reference");
};
i.m1();
}
}
```
### with method reference
```java
interface Interf{
public void m1();
}
class Test{
public static void m2(){
System.out.println("Method reference");
public static void main(String [] args){
Interf i= Test::m2 ;
i.m1();
}
}
```

**Refered method and referring method must have same argument type. Mthod return type can be different, modifiers can be diff, method can be static or instance.**

## Reference to an Instance Method

like static methods, you can refer instance methods also.
```java
containingObject::instanceMethodName
```
### Example
```java
public class Test {

	public void m1() {
		for (int i = 0; i < 10; i++) {
			System.out.println("Child Thread");
		}
	}
	public static void main(String[] args) {

		Test t = new Test();
		Runnable r = t::m1;
		Thread t1 = new Thread(r);
		t1.start();
		for (int i = 0; i < 10; i++) {
			System.out.println("Main Thread");
		}
	}
}
```


