---
title : 采用MVC的框架开发时业务代码应该放在model还是controller
categories : 
 - php 
tags :
	- PHP
---

这些赞美让她听起来充满了吸引力

## 放在Model层
 
被这个问题困扰了很长时间

对于项目的使用者来说,他们最关心的是项目是否产生收益，或者说如何使项目的收益最大化。基于这个出发点，要求我们开发的项目必须要实用、稳定、流畅、安全。翻译一下就是

	实用：产品功能丰富、可根据市场反馈快速迭代
	稳定：24小时服务
	流畅：响应迅速
	安全：保护隐私

So,任何项目的开发都会围绕`效率`、`质量`。效率意味着代码具有`高复用性`。那么业务代码放在controller中复用性高还是放在model中复用性高呢？--哪复用性高,就写在哪
	
## 如何放在Model层,依据哪些准则

Model （模型）
	
	是应用程序中用于处理应用程序数据逻辑的部分。通常模型对象负责在数据库中存取数据。
	翻译:Model中可以包含业务逻辑，不仅仅负责对数据库的增删改查，或者说Model可以分为两类

		1 数据表    model
        2 业务逻辑  model
	
		model中不允许出现对($_POST,$_GET)变量的操作(解除Model与输入的耦合)

View （视图）

	是应用程序中处理数据显示的部分。通常视图是依据模型数据创建的。
	翻译:对数据进行渲染，使数据可读且容易被接受

Controller（控制器）

	应用程序中处理用户交互的部分。通常控制器负责从视图读取数据，控制用户输入，并向模型发送数据。
    翻译:控制器部分主要接收用户参数($_GET,$_POST)，将处理过的数据以参数的形式发送至`Model`层，换取输出数据


	





