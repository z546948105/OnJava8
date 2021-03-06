[TOC]

<!-- Streams -->
# 第十四章 流式编程

<!-- Java 8 Stream Support -->
## 流支持

Java 设计者面临着一个难题。他们拥有着一系列已经存在的库，这些库不仅仅在 Java 库本身中所使用，并且被用户编写的数百万行代码中使用。那他们如何将一个全新的流的基本概念融入到已经存在的库中？

比如一个简单的例子 **Random**，他们只是增加了更多的方法。只要现有方法没有被改变，遗留代码就不会受到干扰。

最大的挑战来自使用接口的库。集合类是其中重要的组成部分，因为你想把一个集合转换为流。如果向接口添加新方法，则会破坏实现接口但未实现新方法的每个类。

Java 8 中引入的解决方案是在[接口](10-Interfaces.md)中添加 **default**（**默认**）方法。通过这种方案，设计者们可以很平滑地将流式（*stream*）方法转换到现有类中。同时，流方法预置的操作几乎满足了我们平常所有的需求。流操作有三种类型：创建流，修改流元素（中间操作, *Intermediate Operations*），消费流元素（终端操作, *Terminal Operations*）。最后一种类型通常意味着收集流元素（通常是到集合中）。

下面我们来看看每一种类型的流操作。

<!-- Stream Creation -->
## 流创建


<!-- Intermediate Operations -->
## 中间操作


<!-- Optional -->
## Optional类


<!-- Terminal Operations -->
## 终端操作


<!-- Summary -->
## 本章小结


<!-- 分页 -->

<div style="page-break-after: always;"></div>
