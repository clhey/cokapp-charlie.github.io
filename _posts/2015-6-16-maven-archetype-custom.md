---
title: 自定义Maven项目骨架
layout: post
tags: 笔记
categories: backend
---

以下用`骨架`代指Maven项目骨架，即archetype。

程序员使用自己定义的`骨架`开启一个新项目的快感不用多提，下面记录一个实用性强的自定义骨架流程。

#从一个原型项目开始
##首先
这个原型项目即是使用我们的骨架新建项目后的基本结构，拷贝原有Maven项目或新建项目都可。
##然后
在该项目pom.xml中，添加`maven-archetype-plugin`插件：
```
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-archetype-plugin</artifactId>
	<version>2.2</version>
</plugin>
```
##最后
在原型项目pom.xml所在目录执行`mvn archetype:create-from-project`，执行完毕后就会在原型项目的generated-sourced/archetype目录生成最基本的`骨架`。如下便是`骨架`的基本目录结构：

其中，*archetype-resources*目录下是原型项目的所有文件，
```
src
├─main
│  └─resources
│      ├─archetype-resources
│      │  └─src
│      │      └─main
│      │          ├─java
│      │          │  ├─controllers
│      │          │  │  └─api
│      │          │  ├─mapper
│      │          │  ├─model
│      │          │  └─service
│      │          ├─resources
│      │          │  ├─config
│      │          │  │  ├─addons
│      │          │  │  │  └─security
│      │          │  │  └─security
│      │          │  ├─mybatis
│      │          │  │  └─__artifactId__
│      │          │  │      └─mappers
│      │          │  ├─spring
│      │          │  │  └─__artifactId__
│      │          │  └─springmvc
│      │          │      └─__artifactId__
│      │          └─webapp
│      │              └─WEB-INF
│      │                  └─freemarker
│      │                      └─__artifactId__
│      │                          └─shenqing
│      └─META-INF
│          └─maven
└─test
    └─resources
        └─projects
            └─basic
```

如果原型项目足够简单，`骨架`就足够使用了，执行`mvn install`之后，我们就可在本地使用该`骨架`开始新项目了。否则继续下一步，进行`骨架`的加工。

#`骨架`的加工

>待续
