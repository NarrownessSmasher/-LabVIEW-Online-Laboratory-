# 　　　　    　 基于LabVIEW的过控实验平台设计
## 概述 
本程序为本科毕设《基于基于LabVIEW的过控实验平台设计》的具体实现，为作者学习LabVIEW近一周之后开始着手设计，设计一周后转向其他学习项目，之后到答辩之前偶尔修修补补，在网友面向晨曦帮助进行了程序的整体结构以及UI优化，从开始到完工横跨两个月。<br>
可供LabVIEW初学者借鉴的主要内容包括：
* 数据库与LabVIEW的ODBC连接
* 登录注册系统设计（关于修改密码之类的功能会有所提及）
* 公告轮播显示功能的实现
* 不同选项卡之间切换的基本实现
* PID调节实验的三种不同实现方式
    * 直接使用LabVIEW的基础控件实现PID实验
    * 使用Matlab脚本节点实现仿真
    * 通过OPC通讯的方式实现LabVIEW和Simulink的联合仿真
* 自动报表功能的实现
    * 自动生成word实验报告（数据+图像）
    * 自动excel报表
* 网友面向晨曦添加的功能较为丰富的用户管理系统（具体功能读者可自行研究2.0版本，不作展示）<br>

## *本设计为简易虚拟实验平台的概念化实现，注重主要功能的实现方式，实用性的提升有待具体的进一步开发。主要在实验过程的主要难点上进行实现，具体内容只要掌握方法都是搬砖过程。*<br>

## ODBC连接
ODBC的连接方式及设置方式以及有无数大佬发过极其详细的帖子了，读者自行百度即可，这里只讲主要思路。<br>
数据库我最初选择的是MySQL,本人对数据库几乎一无所知，所以这里推荐没有数据库基础的朋友使用Navicat For MySQL这款可视化数据库设计软件，可以省去很多麻烦。
<br>这里放几张过程图：<br>
<p align="center">
	<img src="img/Navicat与MySQL建立连接.png" alt="Sample"  width="360" height="500">
	<p align="center">
		<font >Navicat与MySQL建立连接</font>
	</p>
</p>

<p align="center">
	<img src="img/建立信息表.png" alt="建立信息表"  width="500" height="313">
	<p align="center">
		<font >建立信息表</font>
	</p>
</p>

<p align="center">
	<img src="img/进行表设计.png" alt="进行表设计"  width="500" height="329">
	<p align="center">
		<font >进行表设计</font>
	</p>
</p>

<p align="center">
	<img src="img/进行表设计.png" alt="进行表设计"  width="500" height="329">
	<p align="center">
		<font >进行表设计</font>
	</p>
</p>

<p align="center">
	<img src="img/在命令窗口查看已建立数据库.png" alt="在命令窗口查看已建立数据库"  width="500" height="261">
	<p align="center">
		<font >在命令窗口查看已建立数据库</font>
	</p>
</p>

<p align="center">
	<img src="img/建立ODBC数据连接.png" alt="建立ODBC数据连接"  width="500" height="388">
	<p align="center">
		<font >建立ODBC数据连接</font>
	</p>
</p>

<br>这里可能会出现一个问题，32位LabVIEW和64位的其他程序不兼容，可以百度搜索应用程序池，将下图的启用32位程序设置成TRUE可以解决很多32位64位不兼容的问题。

<p align="center">
	<img src="img/进行应用程序默认设置.png" alt="进行应用程序默认设置"  width="360" height="450">
	<p align="center">
		<font >进行应用程序默认设置</font>
	</p>
</p>
=====
## 动图效果展示
