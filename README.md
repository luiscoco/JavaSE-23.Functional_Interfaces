# JavaSE-Functional Interfaces

In Java, a functional interface is an **interface that contains only one abstract method**. 

Functional interfaces are a key concept in Java's functional programming support, and they are used to enable lambda expressions and functional programming idioms.

Let's break this down with an example. Suppose you have the following functional interface:

```java
@FunctionalInterface
interface MyFunctionalInterface {
    void myAbstractMethod();

    // You can have default and static methods as well
    default void myDefaultMethod() {
        System.out.println("Default method");
    }

    static void myStaticMethod() {
        System.out.println("Static method");
    }
}
```

Here, MyFunctionalInterface is a functional interface because it has only one abstract method, which is myAbstractMethod(). 

The @FunctionalInterface annotation is optional but serves as a helpful compiler check to ensure the interface adheres to the functional interface requirements.

Now, you can use a lambda expression to instantiate this interface:

```java
public class Main {
    public static void main(String[] args) {
        // Using a lambda expression to implement the abstract method
        MyFunctionalInterface myFunctionalInterface = () -> {
            System.out.println("Implementing myAbstractMethod");
        };

        // Calling the abstract method using the lambda expression
        myFunctionalInterface.myAbstractMethod();

        // Calling the default method
        myFunctionalInterface.myDefaultMethod();

        // Calling the static method
        MyFunctionalInterface.myStaticMethod();
    }
}
```

In this example, the lambda expression ( ) -> { System.out.println("Implementing myAbstractMethod"); } is used to provide an implementation for the abstract method of the functional interface. 

This is the power of functional interfaces—they allow you to treat functionality as a first-class citizen and use it concisely.

Remember, a functional interface can only have one abstract method, but it can have multiple default or static methods without breaking the rule.

I hope this clarifies the concept of functional interfaces in Java! Let me know if you have further questions or if you'd like more examples.
