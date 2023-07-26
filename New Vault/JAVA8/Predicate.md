# Predicate Fucntional Interface
It is a functional interface which represents a predicate (boolean-valued function) of one argument. 
It is defined in the java.util.function package and contains test() a functional method.
A predicate is a function with a single argument and returns boolean value.
1. To implement predicate functions in Java, Oracle people introduced Predicate interface in 1.8 version (i.e.,Predicate<T>).
2. Predicate interface present in Java.util.function package.
3. It’s a functional interface and it contains only one method i.e., test().
4. 
   ```java   
   interface Predicate<T> {
   public boolean test(T t);
 }
 ```
 
 *Write a predicate to check whether the given integer is greater than 10 or not.*

```java
import Java.util.function; 
 class Test { 
 public static void main(String[] args) { 
 predicate<Integer> p = I  (i>10); 
 System.out.println(p.test(100)); 
 System.out.println(p.test(7)); 
 System.out.println(p.test(true)); //CE incompatible types
 } 
 }
```
# Predicate joining
It’s possible to join predicates into a single predicate by using the following methods.
1. **default Predicate<T> and(Predicate<? super T> other)** -- It returns a composed predicate that represents a short-circuiting logical AND of this
 predicate and another. When evaluating the composed predicate, if this predicate is false, then the other predicate is not evaluated.
2. **default Predicate<T> or(Predicate<? super T> other)** -- It returns a composed predicate that represents a short-circuiting logical OR of this
 predicate and another. When evaluating the composed predicate, if this predicate is true, then the other predicate is not evaluated.
3. **default Predicate<T> negate()** -- It returns a predicate that represents the logical negation of this predicate.
   
these are exactly same as logical AND ,OR complement operators

```java
import Java.util.function.*; 
 class test { 
 public static void main(string[] args) { 
 int[] x = {0, 5, 10, 15, 20, 25, 30}; 
 predicate<integer> p1 = i->i>10; 
 predicate<integer> p2=i -> i%2==0; 
 System.out.println("The Numbers Greater Than 10:"); 
 m1(p1, x); 
 System.out.println("The Even Numbers Are:"); 
 m1(p2, x); 
 System.out.println("The Numbers Not Greater Than 10:"); 
 m1(p1.negate(), x); 
 System.out.println("The Numbers Greater Than 10 And Even Are:â€•); 
 m1(p1.and(p2), x); 
 System.out.println("The Numbers Greater Than 10 OR Even:â€•); 
 m1(p1.or(p2), x); 
 }
public static void m1(predicate<integer>p, int[] x) { 
 for(int x1:x) { 
 if(p.test(x1)) 
 System.out.println(x1); 
 } 
 } 
 }
```

 **static <T> Predicate<T> isEqual(Object targetRef)** -- It returns a predicate that tests if two arguments are equal according to 
 Objects.equals(Object, Object).

 ```java

Predicate<Employee> isCEO=Predicate.isEqual(new Employee("Durga","CEO",30000,"
Hyderabad")); 
 
 Employee e1=new Employee("Durga","CEO",30000,"Hyderabad"); 
 Employee e2=new Employee("Sunny","Manager",20000,"Hyderabad"); 
 System.out.println(isCEO.test(e1));//false  bcoz objects are diff although they have same values (it uses equals() method of Object class)
 System.out.println(isCEO.test(e2));//false
```
   
