



## 面试题

### 1、Callable和Runnable的区别

**相同点：**

1. 两者都是接口
2. 两者都需要调用Thread.start启动线程

**不同点：**

1. callable的核心是call方法，允许返回值，runnable的核心是run方法，没有返回值
2. call方法可以抛出异常，但是run方法不行
3. 因为runnable是java1.1就有了，所以他不存在返回值，后期在java1.5进行了优化，就出现了callable，就有了返回值和抛异常
4. callable和runnable都可以应用于executors。而thread类只支持runnable


