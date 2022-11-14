---
title: 'Python的selenium在ubuntu上遇到的版本问题报错'
date: 2020-12-25 13:59:58
tags: [Python]
categories: [工作上的思考]
---
今天开脚本的时候莫名其妙的跳出来这个错误，之前一直好好的，不太清楚到底问题出在哪里。
```
>selenium.common.exceptions.SessionNotCreatedException: Message: session not created: This version of ChromeDriver only supports Chrome version 80
```
检查了下自己的Chrome浏览器版本是‘83.0.4103.97（正式版本） （64 位）’

最后在Stackoverflow上面搜到一个解决方案：使用webdriver-manager这个库来管理，成功解决问题
```
>pip install webdriver-manager
```
安装完运行测试
```
>from selenium import webdriver
>from webdriver_manager.chrome import ChromeDriverManager
>driver = webdriver.Chrome(ChromeDriverManager().install())
```
不需要每次都下载图像。webdriver_manager中有一个缓存机制，因此，如果可能，它将使用上一次运行中webdriver_manager下载的计算机上的正确驱动程序