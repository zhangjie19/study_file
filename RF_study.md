# RobotFramework

## 一、简介和特点

简介：RF是一个基于python语言开发的，可扩展的，是以关键字驱动模式的自动化测试框架，当前最新版要求`python3.7`

关键字驱动和数据驱动的区别？

- 关键字驱动：关键字驱动表示把项目中的一些逻辑封装成关键字(一个函数名)，login，register，dingdan，Set Viriable，调用不同的关键字组合实现不同的业务逻辑，从而驱动测试用例执行。

- 数据驱动：数据驱动是把测试用例里面的数据提取到excel或者yaml文件里面，然后通过改变excel或者yaml中的数据驱动测试用例执行。

特点：

	1. 编写用例简单，可以以robot、Txt、Tsv、Html的格式编写用例
	1. 自动生成HTML格式的测试报告和日志。
	1. 除了自带的类库之外，还有很多实用的扩展类库。
	1. 可以根据项目需要自定义一些关键字。
	1. 可以使用GUI的方式运行，可以和`SVN`、`GIT`以及`jenkins`持续集成。



## 二、RF环境安装

1. 安装`Python3.7.3`并且还需要设置python的环境变量。

2. 使用管理员的身份打开dos窗口。

   安装`pip install robotframework==3.1`

 3. 在dos窗口中安装RIDE工具。

    `pip install robotframework-ride`

    ![image-20221109195504772](C:\Users\zhangjie\Desktop\学习资料\study_file\img\image-20221109195504772.png)







