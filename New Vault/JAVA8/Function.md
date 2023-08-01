## Function interface
The Function Interface is a part of the java.util.function package which has been introduced since Java 8, to implement functional programming in Java. 
It represents a function which takes in one argument and produces a result. Hence this functional interface takes in 2 generics namely as follows:
```java
interface Function(T,R) { 
 public R apply(T t); 
 }
```
*T*: denotes the type of the input argument 
*R*: denotes the return type of the function

The Function interface consists of the following 4 methods as listed which are later discussed as follows:
1. apply()
2. andThen() -->  default <V> Function<T, V> andThen(Function<? super R, ? extends V> after)
3. compose() -->   default <V> Function<V, R> compose(Function<? super V, ? extends T> before)
4. identity() --->  static <T> Function<T, T> identity()

### Difference between Predicate and Function

Sr | Predicate | Function
---|---|---
1 | To implement conditional checks We should go for predicate | To perform certain operation And to return some result we Should go for function.
2 | Predicate can take one type Parameter which represents Input argument type .Predicate<T> | Function can take 2 type Parameters. First one represent input argument type and Second one represent return Type. Function<T,R>
3 | Predicate interface defines only one method called test() | Function interface defines only one Method called apply().
4 | public boolean test(T t) | public R apply(T t)
5 | Predicate can return only boolean value. | Function can return any type of value

### Example
```java
import java.util.function.*; 
 class Test 
 { 
 public static void main(String[] args) 
 { 
 String s="durga software solutions hyderabad"; 
 Function<String,String> f= s1->s1.replaceAll(" ",""); 
 System.out.println(f.apply(s)); 
 } 
 }
```
## Function chaining
We can combine multiple functions together to form more complex functions.For this Function interface defines the following 2 default methods:
1. f1.andThen(f2): First f1 will be applied and then for the result f2 will be applied.
2. f1.compose(f2)===>First f2 will be applied and then for the result f1 will be applied.

## Function interface Static Method : identity()
Function interface contains a static method.
static <T> Function<T,T> identity()
Returns a function that always returns its input argument
```java
import java.util.function.*; 
 class Test 
 { 
 public static void main(String[] args) 
 { 
 Function<String,String> f1= Function.identity(); 
 String s2= f1.apply("durga"); 
 System.out.println(s2); 
 } 
 }
```
**Output: durga**
