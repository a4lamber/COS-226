# Readme

---

Data structure and algorithm is the bread and butter for any programmer. 如下图所示，数据结构，实际上分成三层概念，
- 基础层
  - 定义：这一层主要由`逻辑结构`和`储存结构`组成
  - 逻辑结构:数据与数据之间的关系.
  - 储存结构:在计算机中怎么储存的.
- 抽象层 Abstract Data Type (ADT)
  - 定义: 通常由一种逻辑结构+一种储存结构组成
  - 例子_1: Array: 线性结构(逻辑结构) + 顺序储存(储存结构)组成;
  - 例子_2: Singly linked: 线性结构(逻辑结构) + 链式储存(储存结构)组成;
- 实现层 Concrete Data Type (CDT)
  - 定义: 将上述的抽象出来的数据结构，具现化的过程;
  - 例子_1: Python `List()` 是一种线性+顺序的数据结构.

```mermaid
flowchart LR
    a0("数据结构")
    b1("逻辑结构")
    b2("存储结构")
    b3("运算")
    c1_1("集合")
    c1_2("线性结构")
    c1_3("树")
    c1_4("图")

    c2_1("顺序储存")
    c2_2("链式储存")
    c2_3("散列储存")
    c2_4("索引储存")

    a0 --> b1
    a0 --> b2
    a0 --> b3
    b1 --> c1_1
    b1 --> c1_2
    b1 --> c1_3
    b1 --> c1_4
    b2 --> c2_1
    b2 --> c2_2
    b2 --> c2_3
    b2 --> c2_4
```


---
<!-- ## Notes
- [recursion](notes/recursion.ipynb)

 -->




<!-- ## Resources for regex
- https://ihateregex.io
- https://regex101.com/r/1paXsy/1
- https://github.com/ziishaned/learn-regex -->


## Other resources
- https://runestone.academy/ns/books/published/pythonds/index.html
- https://blog.csdn.net/Holmofy/article/details/76401074
- [dictionary of algorithms and data structure](https://xlinux.nist.gov/dads/) This site has many definition for terminology used in data structure, especially u r confused about data structure in an academic setting.