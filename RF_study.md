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

4.  双击RIDE图标，或者dos窗口输入ride.py

## 三、RF的使用

1. 创建项目：`new project`

   注意：输入项目名称，选择项目路径，选择Dictionary目录

2. 创建测试套件(它是测试用例的载体) `new Testsuite`

   注意：选择File

3. 创建测试用例 `new Testcase`

4. 创建业务关键字 (资源文件，它是自定义关键字的载体)`new Resource`

   注意：只能在文件夹下面创建，并且是Txt格式，它是自定义关键字的载体

## 五、RF常用类库

1. 标准库：不需要安装，直接用，RF自带
   - Buitini（测试库）
   - Collections（集合库）
   - Date Time（时间）
   - ScreenShot（截屏）

2. 扩展库：需要通过pip安装库
   - Web自动化测试：SeleniumLibrary，Selenium2Library，SeleniumLibrary for java等
   - API接口自动化：RequestsLibrary
   - APP自动化测试：AppiumLibrary

## 六、RF常用关键字的使用

- 快捷键
  1. 搜索关键字：F5
  2. 自动补全关键字：Ctrl+Shift+空格
  
  关键字用法：
  
  | 关键字                | 用法             |
  | --------------------- | ---------------- |
  | Log                   | 打印日志         |
  | Comment               | 注释             |
  | Set Variable          | 设置变量         |
  | Get Time              | 获取时间         |
  | Catenate              | 字符串拼接       |
  | Create List           | 创建列表         |
  | Create Dictionary     | 创建字典         |
  | Get Dictionary Keys   | 获取字典Key值    |
  | Get Dictionary Values | 获取字典value值  |
  | Get From Dictionary   | 根据key获取value |
  | Evaluate              | 执行python方法   |

​		![image-20221114233604206](.\img\image-20221114233604206.png)

![image-20221114233621051](.\img\image-20221114233621051.png)

 ![image-20221114233659743](.\img\image-20221114233659743.png)
