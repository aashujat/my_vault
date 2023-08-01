## Consumer interface
It represents a function which takes in one argument and produces a result. However these kind of functions don’t return any value.Sometimes our requirment is 
we have to provide some input value, perform certain operation, but not required to return anything,then we should go for Consumer.i.e Consumer can be used to 
consume object and perform certain operation.
```java
 interface Consumer<T> 
 { 
 public void accept(T t); 
 }
```
### Example

```java
import java.util.function.Consumer; 
 class Test 
 { 
 public static void main(String[] args) 
 { 
 Consumer<String> c=s->System.out.println(s); 
 c.accept("Hello"); 
 c.accept("DURGASOFT"); 
 } 
 }
```
**Output:
Hello
DURGASOFT**

## Consumer Chaining:   
default Consumer <T>  andThen(Consumer<? super T> after)
Just like Predicate Chaining and Function Chaining, Consumer Chaining is also possible. For this Consumer Functional Interface contains default method andThen().
c1.andThen(c2).andThen(c3).accept(s)
First Consumer c1 will be applied followed by c2 and c3.
