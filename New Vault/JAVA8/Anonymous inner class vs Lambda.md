## Anonymous inner Class vs Lambda function

whenever there is a annonymous inner class is used, it might be replaced by lambda functions in some cases.A praticular case of inner class can be replaced by lambdaExpression.
If an annonymous inner class implement an interface which contains only one abtract method(*Functional interface*) then it can be replaced by *Lambda Expression*.


**Multithreading using Annonymous inner class**
```java
public class ThreadDemo {

	public static void main(String[] args) {
		 
		Runnable r=new Runnable() {
			
			@Override
			public void run() {
				for(int i=0;i<10;i++) {
					System.out.println("Child Thread");
				}
				
			}
		};
		Thread t=new Thread(r);
		t.start();
		for(int i=0;i<10;i++) {
			System.out.println("Main Thread");
		}

	}

}
```
**Multithreading using Lambda function**

```java

Runnable r = () -> {

			for (int i = 0; i < 10; i++) {
				System.out.println("Child Thread");
			}
		};
```

*OR*
```java
Thread t = new Thread( () -> {

			for (int i = 0; i < 10; i++) {
				System.out.println("Child Thread");
			}
		}
  );
```

## Difference between Anonymous inner class and Lambda Expression

### Anonymous inner class
1. It is a class without name.
2. It can extend abstract and concrete class.
3. It can implement interface that contain any number of abstract methods.
4. Inside Anonymous inner class we can define instance variables.
5. It can be instatntiated.
6. Inside Anonymous inner class **this** always refers to Anonymous inner class object but not outer class object.
7. It is best choice if we want to handle  ultiple methods.
8. For the Anonymous inner class, at time of compilaton a separate .class file will be generated.
9. memory will be allocated whenever we are creating objects.
### Lambda Expressions
1. It is a fucntipn withpout name.
2. It can't extend abstrct and concrete class.
3. It can implement an interface which contains single abstract method(Fucntional Inteface).
4. Inside Lambda Expressions we cant declare instance variables, whatever variables declared are considered as local variable
5. It can't be instantiated.
6.  Inside Lambda Expressions, **this** always refers current outer class object, i.e. enclosing class object.
7.  Lambda Expressions is best choice if we want to handle Fucntional interface.
8.  For the Lambda Expressions at time of compilation of no separate .class file will be created.
9.  Lambda Expressions will reside in permanent memory of JVM.
