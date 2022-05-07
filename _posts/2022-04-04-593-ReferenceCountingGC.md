---
layout: post
title: JVM ReferenceCountingGC
pid: 593
tags: [java]

---

```java
public class ReferenceCountingGC {
    public Object instance = null;
    private static final int _1MB = 1024 * 1024;

    private byte[] bigSize = new byte[2  * _1MB];

    public static void testGC() {
        ReferenceCountingGC objA = new ReferenceCountingGC();
        ReferenceCountingGC objB = new ReferenceCountingGC();
        objA.instance = objB;
        objB.instance = objA;

        objA = null;
        objB = null;

        System.gc();
    }

    public static void main(String[] args) {
        testGC();
    }
}
```




```java
baoguo@MacBook-Pro java % java -XX:+PrintGCDetails  ReferenceCountingGC
[GC (System.gc()) [PSYoungGen: 6717K->496K(76288K)] 6717K->504K(251392K), 0.0006260 secs] [Times: user=0.00 sys=0.00, real=0.00 secs] 
[Full GC (System.gc()) [PSYoungGen: 496K->0K(76288K)] [ParOldGen: 8K->267K(175104K)] 504K->267K(251392K), [Metaspace: 2499K->2499K(1056768K)], 0.0024706 secs] [Times: user=0.02 sys=0.01, real=0.00 secs] 
Heap
 PSYoungGen      total 76288K, used 655K [0x000000076ab00000, 0x0000000770000000, 0x00000007c0000000)
  eden space 65536K, 1% used [0x000000076ab00000,0x000000076aba3ee8,0x000000076eb00000)
  from space 10752K, 0% used [0x000000076eb00000,0x000000076eb00000,0x000000076f580000)
  to   space 10752K, 0% used [0x000000076f580000,0x000000076f580000,0x0000000770000000)
 ParOldGen       total 175104K, used 267K [0x00000006c0000000, 0x00000006cab00000, 0x000000076ab00000)
  object space 175104K, 0% used [0x00000006c0000000,0x00000006c0042df8,0x00000006cab00000)
 Metaspace       used 2506K, capacity 4486K, committed 4864K, reserved 1056768K
  class space    used 267K, capacity 386K, committed 512K, reserved 1048576K
baoguo@MacBook-Pro java % 
```

