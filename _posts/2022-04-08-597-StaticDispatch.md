---
layout: post
title: JVM StaticDispatch
pid: 597
tags: [java]

---

```java
public class StaticDispatch {
    static abstract class Human {
    }

    static class Man extends Human {
    }

    static class Woman extends Human {
    }

    public void sayHello(Human guy) {
        System.out.println("hello, guy!");
    }

    public void sayHello(Man guy) {
        System.out.println("hello, gentleman!");
    }

    public void sayHello(Woman guy) {
        System.out.println("hello, lady!");
    }

    public static void main(String[] args) {
        Human man = new Man();
        Human woman = new Woman();
        StaticDispatch sr = new StaticDispatch();
        sr.sayHello(man);
        sr.sayHello(woman);
    }
 }
```




```java
public class StaticDispatch1 {
    static class Human {
        public void sayHello() {
            System.out.println("hello, guy!");
        }
    }

    static class Man extends Human {
        public void sayHello() {
            System.out.println("hello, gentleman!");
        }
    }

    static class Woman extends Human {
        public void sayHello() {
            System.out.println("hello, lady!");
        }
    }

    public static void main(String[] args) {
        Human human = new Human();
        human.sayHello();

        human = new Man();
        human.sayHello();

        human = new Woman();
        human.sayHello();
    }
}
```

