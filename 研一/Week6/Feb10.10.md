#见导师#

----------

任务，寒假发一篇文章，

10月底，实现Android客户端

一周三篇文章并做笔记

本星期实现历史数据的选择！！！！！！！！！！！

-----------
论文《基于云平台的工业现场数据发布系统》72页

系统所用软件/工具：
	
	vs2013,C#,SQL Server ,SQL Azure云数据库，Windows Azure数据平台，ASP.NET
	进行数据访问，

章节介绍：

1.第一章
	
绪论，主要是阐述本课题的研究背景、国内外污水处理厂的一些现状、研究的目的及意义以及本课题需要完成的内容，并对本课题进行了系统的介绍。

2.第二章为基于云平台的工业现场数据发布的分析研究，主要是介绍系统的工业现场分布、云监测平台的主要的功能以及与传统工业监控相比本文的监控系统的一系列功能优势所在，并对现有的技术方案进行了介绍和分析。

3.第三章为基于云平台的数据发布的核心技术，主要开发现场设备的通信技术、WebSocket 通信技术以及 WindowsAzure 微软云技术，并对本系统的数据库进行介绍、创建以及对数据的操作，为基于云平台的工业数据发布系统提供了很好的技术支持。

4.第四章为工业的现场数据发布具体的实现，主要介绍系统的整体框架、云平台中数据的储存以及应用程序的运行等功能的一些具体的应用，工业现场 PLC的一些数据的交换、数据库的三层搭建一些具体的应用、本地数据库与云数据库数据的同步以及在云平台上部署网站的一些操作。

5.第五章为基于云平台的工业现场数据发布系统的运行结果，对污水处理厂的整体控制工艺进行设计，分析工业现场数据发布系统的整体结构，对污水处理厂的数据显示以及结果进行分析，反映出本系统的优势所在，并验证了在论文中提到的观点。

6.第六章为总结与展望，主要总结了本课题所做的工作。并且针对本系统存在的不足，提出对基于云平台的工业现场发布系统的进一步的改进和完善。


----------
**系统架构图：**
	
	云平台检测层——
		服务发布，数据操作，用户权限管理，检测服务，平台搭建，运营维护
	Web服务层——
		用户注册/登录，添加/删除现场，用户权限申请，添加/删除设备，实时检测服务，历史数据服务
	现场检测服务层——
		仪表数据采集，PLC数据采集


**技术方案**

单机服务器构架

C/S构架：
	
*B/S构架:包含数据库服务器，网站服务器和浏览器实现系统的跨平台性，就有良好的实时性，*


**现场设备检测技术**

（1） NetBEUI通信技术； 不能用来对外网进行通信，不具有路由功能。

（2）IPX及其兼容技术；针对实现路由功能而设计的协议，适合于大型网络使用

（3）TCP/IP通信技术；进行不同网络之间的通讯

----

**3.2基于互联网的实时显示技术**

1.Ajax 异步通信技术，避免http协议在数据交换过程中，因信息过多而导致数据显示不能实时刷新的情况
