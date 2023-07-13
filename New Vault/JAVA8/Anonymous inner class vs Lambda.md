## Anonymous inner Class vs Lambda function

whenever there is a annonymous inner class is used, it may be replaced by lambda functions.


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
