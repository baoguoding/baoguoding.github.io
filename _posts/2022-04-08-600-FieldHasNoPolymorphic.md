---
layout: post
title: JVM FieldHasNoPolymorphic
pid: 600
tags: [java]

---

```java
public class FieldHasNoPolymorphic {
    static class Father {
        public int money = 1;
        public Father() {
            money = 2;
            showMeTheMoney();
        }

        public void showMeTheMoney() {
            System.out.println("I am Father, i have $" + this.money);
        }
    }

    static class Son extends Father {
        public int money = 3;

        public Son() {
            money = 4;
            showMeTheMoney();
        }

        public void showMeTheMoney() {
            System.out.println("I am Son, i have $" + money);
        }
    }

    public static void main(String[] args) {
        Father guy = new Son();
        System.out.println("This guy has $" + guy.money);
    }

}

```




```java

```

