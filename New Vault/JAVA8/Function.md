## Function interface
The Function Interface is a part of the java.util.function package which has been introduced since Java 8, to implement functional programming in Java. 
It represents a function which takes in one argument and produces a result. Hence this functional interface takes in 2 generics namely as follows:
```java
interface Function(T,R) { 
2) public R apply(T t); 
3) }
```
*T*: denotes the type of the input argument
*R*: denotes the return type of the function

The Function interface consists of the following 4 methods as listed which are later discussed as follows:
1. apply()
2. andThen()
3. compose()
4. identity()

### Difference between Predicate and Function

Sr | Predicate | Function
---|---|---
1 | To implement conditional checks We should go for predicate | To perform certain operation And to return some result we Should go for function.
2 | Predicate can take one type
Parameter which represents
Input argument type.
Predicate<T> | Function can take 2 type Parameters.
First one represent Input argument 
type and Second one represent return 
Type. 
Function<T,R>
3 | 1.89 | 6
4 | 1.89 | 6
