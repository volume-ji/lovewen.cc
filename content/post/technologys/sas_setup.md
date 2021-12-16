+++
title = "win10安装SAS9.3"
date = "2021-11-20T01:45:53+08:00"
tags = ["数据分析", "SAS"]
series = ["技术相关"]
dropCap = false
indent = true
thumbnail = "/images/technologys/sas/sas.png"
+++

# win10安装SAS9.3版本

## SAS9.3 64位下载

百度网盘

链接: https://pan.baidu.com/s/1ThD7YrNi3VxsO6q4dmfB-Q 

提取码: au3r

## 准备工作

* win10操作系统
* 因为该版本SID有效时间为2018-03-16 ～ 2019-02-28，需要调整系统时间为这两个时间之间

## sas9.3安装

### 解压

1. 从网盘下载好压缩包之后解压即可。

### 安装

1. 从解压文件里找到setup.exe文件，以管理员权限打开

![setup.exe](/images/technologys/sas/xuan_ze_exe.png)

2. 选择"安装sas软件"

![安装sas](/images/technologys/sas/an_zhuang.png)

3. 指定安装位置，默认是C盘，软件比较大，可以考虑换成D盘

![安装位置](/images/technologys/sas/sas_location.png)

4. 如图选择"安装相关软件"

![相关软件](/images/technologys/sas/setup_software.png)

5. 选择安装产品，如图

![安装产品](/images/technologys/sas/setup_product.png)

6. 根据操作系统64/32位选择，这里选择64位

7. 产品项目选择的时候全选

![全选项目](/images/technologys/sas/choose_item.png)

8. 注意选择sid文件的时候，需要指定网盘下载包里的文件"SAS93_9BXQYC_12002075_Win_X64_Wrkstn.txt"

![sid选择](/images/technologys/sas/sas_sid.png)

9. 指定ie浏览器位置

![ie浏览器](/images/technologys/sas/iexplore.png)
 
10. 选择SAS推荐安装的java

![java](/images/technologys/sas/java.png)

11. 取消开机自动启动

![取消开机自启](/images/technologys/sas/cancel_autostart.png)

12. 输入sas的url: http://localhost:8080/saslogon/sas-enviroment.xml

![url](/images/technologys/sas/sas_url.png)

13. 接下来扫描准备，完成后点击下一步等待模块安装（接近半小时，耐心等待）。

14. 如果安装有模块错误，可能需要卸载重新安装下。注意卸载后需要把安装目录所有文件夹全部清理

### 启动
如果安装时发现只有一个java模块出错或者使用时有发现提示虚拟机无法加载的情况，请参考该链接：
https://bbs.pinggu.org/thread-5724907-1-1.html

1. 查找java安装版本，可以在cmd上使用java -version查看（需要提前配置java环境变量）

![java版本](/images/technologys/sas/java_version.jpeg)
2. 在安装目录D:\Program Files\SASHome\SASFoundation\9.3\nls下面一共有4个文件夹，1d，en，u8，zh，每个文件夹下面都有sasv9，打开后修改两处
* 第一处
  -Dsas.jre.libjvm=C:\PROGRA~2\Java\JRE7\bin\client\jvm.dll

![](/images/technologys/sas/java_modify1.jpeg)
* 第二处 
  -SET DTJ_CLASSPATH "D:\Program Files\SASHome\SASFoundation\9.3\dmine\sasmisc\dtj.jar;C:\Program Files (x86)\Java\jre7\lib\rt.jar"

![java修改](/images/technologys/sas/java_modify2.png)
