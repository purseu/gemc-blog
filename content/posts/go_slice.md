---
title: "Go_slice"
date: 2021-10-04T10:53:18+08:00
categories:
- GoLang
- Slice
tags:
- Go
- Slice
keywords:
- Slice
#thumbnailImage: //example.com/image.jpg
---

```markdown
1. slice不能比较
2. make函数可以创建一个指定元素类型、长度和容量的slice
    make([]T, len)
    make([]T, len, cap) == make([]T, cap)[:len]
```
<!--more-->

```markdown
1. 一个零值的slice等于nill
2. 一个nil值的slice没有底层数组
3. 一个nil值的slice的长度和容量都是0
```
### append

```markdown
1. append函数向slice追加元素
```