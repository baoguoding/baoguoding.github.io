---
layout: post
title: JVM JavaVMStackOOM
pid: 592
tags: [java]

---

```java
public class JavaVMStackOOM {
    private void dontStop() {
        while(true) {

        }
    }

    public void stackLeakByThread() {
        while (true) {
            Thread thread = new Thread(new Runnable() {
                @Override
                public void run() {
                    dontStop();
                }
            });
            thread.start();
        }
    }

    public static void main(String[] args) throws Throwable{
        JavaVMStackOOM oom = new JavaVMStackOOM();
        oom.stackLeakByThread();
    }
}
```




```java
baoguo@MacBook-Pro java % javac JavaVMStackOOM.java 
baoguo@MacBook-Pro java % java -Xss2M JavaVMStackOOM
Exception in thread "main" java.lang.OutOfMemoryError: unable to create new native thread
        at java.lang.Thread.start0(Native Method)
        at java.lang.Thread.start(Thread.java:717)
        at JavaVMStackOOM.stackLeakByThread(JavaVMStackOOM.java:16)
        at JavaVMStackOOM.main(JavaVMStackOOM.java:22)
^CJava HotSpot(TM) 64-Bit Server VM warning: Exception java.lang.OutOfMemoryError occurred dispatching signal SIGINT to handler- the VM may need to be forcibly terminated
^CJava HotSpot(TM) 64-Bit Server VM warning: Exception java.lang.OutOfMemoryError occurred dispatching signal SIGINT to handler- the VM may need to be forcibly terminated



```

