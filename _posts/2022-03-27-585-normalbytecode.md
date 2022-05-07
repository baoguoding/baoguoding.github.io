---
layout: post
title: JVM 常见字节码
pid: 585
tags: [java]

---

```java
public class MethodDemo {
    //构造方法
    public MethodDemo(){

    }
    //私有方法
    private void methodPrivate(){

    }
    //final方法
    public final void methodFinal(){

    }
    //静态方法
    public static void methodStatic(){

    }

    public static void main(String[] args) {
        //创建对象
        MethodDemo demo = new MethodDemo();
        //调用方法
        demo.methodPrivate();
        demo.methodFinal();
        demo.methodStatic();

        MethodDemo.methodStatic();
    }
}
```




```java
/Library/Java/JavaVirtualMachines/jdk1.8.0_291.jdk/Contents/Home\bin\javap -v MethodDemo
Classfile /Users/baoguo/codes/demo/target/classes/MethodDemo.class
  Last modified Mar 27, 2022; size 701 bytes
  MD5 checksum 49241be3842b5be33e991101751bcffa
  Compiled from "MethodDemo.java"
public class MethodDemo
  minor version: 0
  major version: 52
  flags: ACC_PUBLIC, ACC_SUPER
Constant pool:
   #1 = Methodref          #7.#26         // java/lang/Object."<init>":()V
   #2 = Class              #27            // MethodDemo
   #3 = Methodref          #2.#26         // MethodDemo."<init>":()V
   #4 = Methodref          #2.#28         // MethodDemo.methodPrivate:()V
   #5 = Methodref          #2.#29         // MethodDemo.methodFinal:()V
   #6 = Methodref          #2.#30         // MethodDemo.methodStatic:()V
   #7 = Class              #31            // java/lang/Object
   #8 = Utf8               <init>
   #9 = Utf8               ()V
  #10 = Utf8               Code
  #11 = Utf8               LineNumberTable
  #12 = Utf8               LocalVariableTable
  #13 = Utf8               this
  #14 = Utf8               LMethodDemo;
  #15 = Utf8               methodPrivate
  #16 = Utf8               methodFinal
  #17 = Utf8               methodStatic
  #18 = Utf8               main
  #19 = Utf8               ([Ljava/lang/String;)V
  #20 = Utf8               args
  #21 = Utf8               [Ljava/lang/String;
  #22 = Utf8               demo
  #23 = Utf8               MethodParameters
  #24 = Utf8               SourceFile
  #25 = Utf8               MethodDemo.java
  #26 = NameAndType        #8:#9          // "<init>":()V
  #27 = Utf8               MethodDemo
  #28 = NameAndType        #15:#9         // methodPrivate:()V
  #29 = NameAndType        #16:#9         // methodFinal:()V
  #30 = NameAndType        #17:#9         // methodStatic:()V
  #31 = Utf8               java/lang/Object
{
  public MethodDemo();
    descriptor: ()V
    flags: ACC_PUBLIC
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #1                  // Method java/lang/Object."<init>":()V
         4: return
      LineNumberTable:
        line 5: 0
        line 7: 4
      LocalVariableTable:
        Start  Length  Slot  Name   Signature
            0       5     0  this   LMethodDemo;

  public final void methodFinal();
    descriptor: ()V
    flags: ACC_PUBLIC, ACC_FINAL
    Code:
      stack=0, locals=1, args_size=1
         0: return
      LineNumberTable:
        line 15: 0
      LocalVariableTable:
        Start  Length  Slot  Name   Signature
            0       1     0  this   LMethodDemo;

  public static void methodStatic();
    descriptor: ()V
    flags: ACC_PUBLIC, ACC_STATIC
    Code:
      stack=0, locals=0, args_size=0
         0: return
      LineNumberTable:
        line 19: 0

  public static void main(java.lang.String[]);
    descriptor: ([Ljava/lang/String;)V
    flags: ACC_PUBLIC, ACC_STATIC
    Code:
      stack=2, locals=2, args_size=1
         0: new           #2                  // class MethodDemo
         3: dup
         4: invokespecial #3                  // Method "<init>":()V
         7: astore_1
         8: aload_1
         9: invokespecial #4                  // Method methodPrivate:()V
        12: aload_1
        13: invokevirtual #5                  // Method methodFinal:()V
        16: aload_1
        17: pop
        18: invokestatic  #6                  // Method methodStatic:()V
        21: invokestatic  #6                  // Method methodStatic:()V
        24: return
      LineNumberTable:
        line 23: 0
        line 25: 8
        line 26: 12
        line 27: 16
        line 29: 21
        line 30: 24
      LocalVariableTable:
        Start  Length  Slot  Name   Signature
            0      25     0  args   [Ljava/lang/String;
            8      17     1  demo   LMethodDemo;
    MethodParameters:
      Name                           Flags
      args
}
SourceFile: "MethodDemo.java"

Process finished with exit code 0

```









