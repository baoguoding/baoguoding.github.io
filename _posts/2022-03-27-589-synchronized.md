---
layout: post
title: JVM synchronized
pid: 589
tags: [java]

---

```java
public class Test {
    public static void main(String[] args) {
        Object lock = new Object();
        synchronized (lock) {
            System.out.println("hello");
        }
    }
}
```




```java
/Library/Java/JavaVirtualMachines/jdk1.8.0_291.jdk/Contents/Home\bin\javap -v Test
Classfile /Users/baoguo/codes/demo/target/classes/Test.class
  Last modified Mar 27, 2022; size 704 bytes
  MD5 checksum bcbc680d8ff557e2be9701d84a5c1e52
  Compiled from "Test.java"
public class Test
  minor version: 0
  major version: 52
  flags: ACC_PUBLIC, ACC_SUPER
Constant pool:
   #1 = Methodref          #2.#27         // java/lang/Object."<init>":()V
   #2 = Class              #28            // java/lang/Object
   #3 = Fieldref           #29.#30        // java/lang/System.out:Ljava/io/PrintStream;
   #4 = String             #31            // hello
   #5 = Methodref          #32.#33        // java/io/PrintStream.println:(Ljava/lang/String;)V
   #6 = Class              #34            // Test
   #7 = Utf8               <init>
   #8 = Utf8               ()V
   #9 = Utf8               Code
  #10 = Utf8               LineNumberTable
  #11 = Utf8               LocalVariableTable
  #12 = Utf8               this
  #13 = Utf8               LTest;
  #14 = Utf8               main
  #15 = Utf8               ([Ljava/lang/String;)V
  #16 = Utf8               args
  #17 = Utf8               [Ljava/lang/String;
  #18 = Utf8               lock
  #19 = Utf8               Ljava/lang/Object;
  #20 = Utf8               StackMapTable
  #21 = Class              #17            // "[Ljava/lang/String;"
  #22 = Class              #28            // java/lang/Object
  #23 = Class              #35            // java/lang/Throwable
  #24 = Utf8               MethodParameters
  #25 = Utf8               SourceFile
  #26 = Utf8               Test.java
  #27 = NameAndType        #7:#8          // "<init>":()V
  #28 = Utf8               java/lang/Object
  #29 = Class              #36            // java/lang/System
  #30 = NameAndType        #37:#38        // out:Ljava/io/PrintStream;
  #31 = Utf8               hello
  #32 = Class              #39            // java/io/PrintStream
  #33 = NameAndType        #40:#41        // println:(Ljava/lang/String;)V
  #34 = Utf8               Test
  #35 = Utf8               java/lang/Throwable
  #36 = Utf8               java/lang/System
  #37 = Utf8               out
  #38 = Utf8               Ljava/io/PrintStream;
  #39 = Utf8               java/io/PrintStream
  #40 = Utf8               println
  #41 = Utf8               (Ljava/lang/String;)V
{
  public Test();
    descriptor: ()V
    flags: ACC_PUBLIC
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #1                  // Method java/lang/Object."<init>":()V
         4: return
      LineNumberTable:
        line 1: 0
      LocalVariableTable:
        Start  Length  Slot  Name   Signature
            0       5     0  this   LTest;

  public static void main(java.lang.String[]);
    descriptor: ([Ljava/lang/String;)V
    flags: ACC_PUBLIC, ACC_STATIC
    Code:
      stack=2, locals=4, args_size=1
         0: new           #2                  // class java/lang/Object
         3: dup
         4: invokespecial #1                  // Method java/lang/Object."<init>":()V
         7: astore_1
         8: aload_1
         9: dup
        10: astore_2
        11: monitorenter
        12: getstatic     #3                  // Field java/lang/System.out:Ljava/io/PrintStream;
        15: ldc           #4                  // String hello
        17: invokevirtual #5                  // Method java/io/PrintStream.println:(Ljava/lang/String;)V
        20: aload_2
        21: monitorexit
        22: goto          30
        25: astore_3
        26: aload_2
        27: monitorexit
        28: aload_3
        29: athrow
        30: return
      Exception table:
         from    to  target type
            12    22    25   any
            25    28    25   any
      LineNumberTable:
        line 3: 0
        line 4: 8
        line 5: 12
        line 6: 20
        line 7: 30
      LocalVariableTable:
        Start  Length  Slot  Name   Signature
            0      31     0  args   [Ljava/lang/String;
            8      23     1  lock   Ljava/lang/Object;
      StackMapTable: number_of_entries = 2
        frame_type = 255 /* full_frame */
          offset_delta = 25
          locals = [ class "[Ljava/lang/String;", class java/lang/Object, class java/lang/Object ]
          stack = [ class java/lang/Throwable ]
        frame_type = 250 /* chop */
          offset_delta = 4
    MethodParameters:
      Name                           Flags
      args
}
SourceFile: "Test.java"

Process finished with exit code 0

```









