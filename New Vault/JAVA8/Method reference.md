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
### Example
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
