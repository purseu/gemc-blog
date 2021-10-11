---
title: "Playwright基本介绍"
date: 2021-10-11T19:55:06+08:00
draft: false
categories:
- Testing
- Playwright
tags:
- 自动化
- UI测试
- Playwright
keywords:
- Playwright
---

Playwright是微软提供的一款自动化测试工具。Playwright为现代web应用提供可靠的端到端测试。Playwright目前之前多种编程语言，包括JavaScript、TypeScript、Python、.NET和Java等。本文章将使用Python作为编程语言进行编写，编辑器使用VsCode。


## Web UI自动化测试

在日常的UI自动化测试中，Selenium是最经常使用的，也是老牌的UI自动化测试工具。其他常见的Web端常见的自动化测试工具还包括Cypress、Puppeteer等，移动端常见的工具是Appium。
这里主要记录Playwright的使用。

### Playwright

Playwright的特点：
```markdown
# 支持所有浏览器
1. Chrome、Firefox、Webkit、Edge
2. 跨平台的测试
3. 移动端测试
4. headless(无UI)和headed
# 快速可靠的执行
1. 自动等待的API
2. 无超时的自动化
3. 快速隔离浏览器上下文
4. 弹性元素选择器
# 强大的自动化
1. 剧作家是一个进程外自动化驱动程序，它不受页面内JavaScript执行范围的限制，可以使用多个页面实现场景自动化。
2. 强大的网络控制。剧作家引入了上下文范围的网络拦截，以存根和模拟网络请求。
3. 现代web特性。剧作家支持通过阴影穿透选择器，地理位置，权限，web工作者和其他现代web api的web组件
4. 覆盖所有场景的功能。支持文件下载和上传，进程外iframes，本机输入事件，甚至暗模式。
```

#### 安装Playwright

由于本文使用的是Python语言，因此安装Playwright非常的容易，只要使用pip进行安装即可。

```shell
# 安装playwright
pip install playwright
```

#### 安装浏览器驱动

Playwright支持自定义浏览器驱动的安装位置，只需要在系统变量中添加`PLAYWRIGHT_BROWSERS_PATH`即可。
Playwright支持多款浏览器包括：Chrome、Firefox、Webkit。

```shell
# 安装浏览器驱动
playwright install
```

安装完成，开始初步的体验吧。将以打开百度首页为例进行使用Playwright。

```python
import asyncio
import time
from playwright.async_api import async_playwright

async def main():
    async with async_playwright() as p:
        browser = await p.firefox.launch(headless=False)
        page = await browser.new_page()
        await page.goto("https://www.baidu.com")
        print(await page.title())
        time.sleep(10)
        await browser.close()

asyncio.run(main())
```

###### 打开百度首页

![avatar](https://gemc-blog-1300411896.cos.ap-shanghai.myqcloud.com/open_baidu.png)

###### 打印标题

![avatar](https://gemc-blog-1300411896.cos.ap-shanghai.myqcloud.com/print_title.png)

Piaywright的基本介绍到此结束。