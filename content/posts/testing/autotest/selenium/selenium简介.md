---
title: "Selenium简介"
date: 2021-10-16T16:39:21+08:00
draft: false
categories:
- Testing
- 自动化测试
- selenium
tags:
- Web UI
- selenium
keywords:
- selenium
---

### Selenium简介

### Selenium安装

1. pip install -U selenium
2. 安装浏览器驱动
   1. edge [microsoft-edge](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/)
   2. chrome [chromedriver](http://chromedriver.storage.googleapis.com/index.html)
   3. firefox [geckodriver](https://github.com/mozilla/geckodriver/releases/)

安装浏览器驱动可以配置一个系统环境，方便日后更新和使用。

### selenium初使用

1. 打开的浏览器是无缓存且默认带有自动化软件控制的警告提示
2. 与所有浏览器的交互都是基于Webdriver实现的
3. 自动化测试技术是使用测试框架实现的非线性代码
4. 框架一般基于关键字驱动或POM为核心而实现

```python
#!/usr/bin/env python
# -----------------------------------
# -*- coding: utf-8 -*-
# @Time     :   2021/10/16 18:55
# @Author   :   Gemc
# @Email    :   ge942812@gmail.com
# @File     :   baidu_home.py
# @Project  :   selenium_demo
# @desc     :
# -----------------------------------

import time
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Edge()
driver.get('https://www.baidu.com')
print(driver.title)
driver.find_element(By.ID, 'kw').send_keys('明天会更好')
driver.find_element(By.ID, 'su').click()
time.sleep(6)
driver.quit()
```

#### 框架优势

1. 冗余的降低
2. 可复用性
3. 维护性

#### 测试框架理念

1. 设计模式
   1. 关键字驱动
   2. POM
   3. ...
2. 数据驱动: Excel/Yaml/json/csv
3. 框架结构
   1. 代码与数据分离
   2. 测试代码与逻辑代码分离

框架的编码不是一成不变的。框架的难度在于框架的设计而不是编码。