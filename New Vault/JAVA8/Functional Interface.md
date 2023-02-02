## Functional Interface

A functional interface is an interface in Java that has **exactly one abstract method**. It can have any number of default and static methods.

A functional interface can be annotated with the `@FunctionalInterface` annotation, which is optional but helps to ensure that the interface is designed as a functional interface.

Some examples of functional interfaces in the Java standard library are `Runnable`, `Callable`, `Comparator`, `Consumer`, `Supplier` and many others.

Functional interfaces are used as the basis for lambda expressions and method references in Java 8. It can be used as the type for a lambda expression or method reference, which can be assigned to a variable, passed as an argument to a method, or returned from a method.

*Example*
1. valid functional interface
```java
@FunctionalInterface
interface Student{
public void abstract age();
}
```

2.  Invalid Functional interface
```java
@FunctionalInterface
interface Student{
public void abstract age();
public void abstract marks();
}
# Compile time error--> unexpected @FunctionaInterface annotation, multiple non overriding abstract methods found


@FunctionalInterface
interface Student{

}

# Compile time error--> unexpected @FunctionaInterface annotation, no abstract method found

```

### Functional interface w.r.t innheritance

1. If an interface extend functional interface  and child interface does not contain any abstract method then child interface is also fucntional interface.
```java
@FunctionalInterface
interface A{
void delete();
}
@FunctionalInterface
interface B extends A{

}
```

2.  In the child interface we can define exactly same parent interface method.
```java
@FunctionalInterface
interface A{
void delete();
}
@FunctionalInterface
interface B extends A{
void delete();
}
```

3. In child interface we can't define any new abstract method otherwise it will result into compile time error.
```java
@FunctionalInterface
interface A{
void add();
}
@FunctionalInterface
interface B extends A{
void delete();
}
# compile time error--> unexpected @FunctionaInterface annotation, multiple non overriding abstract methods found 
```

4. Parent interface A is functional interface but child interface B is not a functional interface.
```java
@FunctionalInterface
interface A{
void add();
}

interface B extends A{
void delete();
}