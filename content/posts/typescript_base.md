---
title: "Typescript基本知识"
date: 2021-10-04T21:36:42+08:00
categories:
- Web
- TypeScript
tags:
- JavaScript
- TypeScript
keywords:
- TypeScript
#thumbnailImage: //example.com/image.jpg
---

TypeScript是 `强类型`版的JavaScript。TypeScript允许在定义变量的同时指定类型。

<!--more-->

### 类型

```markdown
1. number
2. string
3. array
4. boolean
5. function
6. void
7. object
8. any
9. null
10. undefined
11. unknown
12. never
13. interface
```

#### .d.ts

```markdown
1. JS文件 + .d.ts文件 === ts文件
2. .d.ts文件让JS文件继续使用JS文件
```

#### 泛型

```markdown

```

#### 联合类型

```markdown
# 联合类型（Union Types）可以通过管道(|)将变量设置多种类型，赋值时可以根据设置的类型来赋值。
let name: string | number
```