[浅析DDD(领域驱动设计)](https://www.jianshu.com/p/b6ec06d6b594)

[DDD第2篇 - 子域与限界上下文](https://yasinshaw.com/articles/79)

[DDD（领域驱动设计），你必须知道的贫血模型和充血模型](https://cloud.tencent.com/developer/article/1732277)

领域模型无关技术，具有高度的业务抽象性，它能够精确的描述领域中的知识体系；同时它也是独立的，我们还需要学会如何让它具有表达性，让模型彼此之间建立关系，形成完整的领域架构。

```

```



- 基于充血模型的面向对象开发模式是DDD的特点之一，而在平时开发中我们都使用的是MVC 架构是基于贫血模型的面向过程开发风格，也许有同学就会问了，贫血模型和充血模型是的什么呢？

## 贫血模型和充血模型

### 简介

**贫血模型**：

- 定义对象的简单的属性值，没有业务逻辑上的方法（个人理解）没有找到官方解释

**充血模型**

- 充血模型也就是我们在定义属性的同时也会定义方法，我们的属性是可以通过某些方式直接得到属性值，那我们也就可以在对象中嵌入方法直接创建出一个具有属性值的对象。也就是说这个对象不再需要我们在进行进一步的操作，这也就复合了OOP的三大特性之一的封装（个人理解）

### 关于DDD和充血模型的关系

我们在平时进行web开发的时候，就是定义DTO，定义数据库Model，BO等，对其进行get set方法，然后通过service 对Bo对象进行操作，最后通过copy属性持久化数据库和DTO传输。但是如果是充血模型的话，就不用在service进行属性赋值，而是在创建这个对象的时候，进行业务操作，赋予其属性值。这里也就是DDD的思想，这个对象也就是DDD所定义的Entity 或者 value 。Service也就是domianService，由多个Entity 和value 组成，构造最终的领域模型。

![image-20210707131505682](/Users/xiye/Library/Application Support/typora-user-images/image-20210707131505682.png)
