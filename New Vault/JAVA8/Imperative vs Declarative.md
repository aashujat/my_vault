# *Imperative*

1. Focuses on how to perform the operations. 
2. Embraces Object mutability. 
3. This style of programming lists the step by step of instructions on how to achieve an objective. 
4 We write the code on what needs to be done in each step. 
5 Imperative style is used with classic Object Oriented Programming

# *Declarative*

1 Focuses on what is the result you want. 
2 Embraces Object immutability. 
3 Analogous to SQL (Structured Query Languague). 
4 Use the functions that are already part of the library to achieve an objective. 
5 Functional Programming uses the concept of declarative programming.

# Example
## *Removing duplicates from list of integers*



### Imperative 

```java
List<Integer> integerList=Arrays.asList(1,2,31,2,3,2,4,53,2);
List<Integer> uniqueList=new ArrayList();
foreach(Integer integer: integerList){
if(!uniqueList.contains(integer))
uniqueList.add(integer);
}
```

### Declarative

```java
List<Integer> integerList=Arrays.asList(1,2,31,2,3,2,4,53,2);
List<Integer> uniqueList=integerList.stream().distinct().collect(Collectors.toList());
```



