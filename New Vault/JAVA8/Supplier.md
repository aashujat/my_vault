## Supplier interface

It represents a function which does not take in any argument but produces a value of type R. Sometimes our requirement is we have to get some value based on 
some operation like supply Student object, Supply Random Name etc. For this type of requirements we should go for Supplier. Supplier can be used to supply 
items (objects). Supplier won't take any input and it will always supply objects.Supplier Functional Interface contains only one method get().
```java
interface Supplier<R> 
 { 
 public R get(); 
 } 
 ```
Supplier Functional interface does not contain any default and static methods.

## Comparison Table of Predicate, Function, Consumer and Supplier

Property | Predicate | Function | Consumer | Supplier
---|---|---|---|---
Purpose | To take some Input and perform some conditional checks | To take some Input and perform required Operation and return the result | To consume some Input and perform required Operation. It won’t return anything | To supply some Value base on our Requirement.
Bananas | 1.89 | 6 |  |  |
