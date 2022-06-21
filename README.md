## **My Dock Finder**

> 对之前购买的开源版本进行了修改，现打包release版本供享用！（无源码）

**§** ***\*配置要求\****

***最低配置***

o 系统：Windows 7 32位 专业版 （***\*win7家庭普通版不可用\****）

o CPU：主频1GHz及以上 ***\*双线程及以上\****处理器

o 内存：512MB以上

o 显存：256MB以上

**推荐配置**

o 系统：Windows 10 64位 1803和1809两个版本最完美，1903及以上系统移动窗口不能显示模糊效果，LTSB可能运行稳定容易崩溃

o CPU：主频1.5GHz及以上 双核四线程及以上处理器

o 内存：1GB及以上

o 显存：512MB及以上 RTX系列显卡可能最小化动画不稳定（主要没有这样的显卡没法测试<img src="https://s2.loli.net/2022/06/21/8PxKwz7kBsMHSG6.jpg" alt="img" style="zoom:15%;" />）

**§** ***\*驱动问题\****（新增）

这个问题是最近发现的适用两年以前包括两年的硬件配置（新配置不知道可自行测试），本人i7-4720 CPU前几天更新Intel官网2020年8月15日最新驱动后DX12最小化无动画，有个朋友更新后dock一天崩溃三到四次而且其他的软件也有bug，然后无意卸载显卡驱动然后***\*使用win10自带的更新安装显卡驱动后，\****DX12恢复最小化动画dock没有崩溃过，所以重点就是显卡驱动问题，***\*不是最新版本驱动就是最好的，\****win10自带更新的驱动是兼容性和稳定性最好的驱动，所以这个方法只适用两年以前的硬件配置，如果是集显建议这样操作，只有独显或者台式机可自行测试

**§** ***\*所需运行库\****

先查看[这个文章](#wechat_redirect)下载DX修复工具修复D3D组件和VC2015-2019运行库，由于MyDock使用VC2019编译必须安装VC2015以上的运行库才可以，Win7系统还要安装文章里面的更新补丁才能开启硬件加速，如果没有这个补丁C++版本MyDock在Win7无法运行（***\*Win7家庭版无法安装这个补丁\****）

Win10系统还需要另外安装组件，首先打开系统设置然后点击应用

![img](https://s2.loli.net/2022/06/21/5uZBFzyTYNngA24.jpg) 

点击右侧可选功能

![img](https://s2.loli.net/2022/06/21/SRXEWs6FB7MJ92O.jpg) 

往下找到图形工具，***\*如果没有【图形工具】点击【+添加功能】然后找到图形工具添加即可\****

![img](https://s2.loli.net/2022/06/21/GXLmqHain14dIDO.jpg)![img](https://s2.loli.net/2022/06/21/Zkq2jfVIMoynri5.jpg) 

***\*下面这个设置自行选择是否打开\****

点击设置更新和安全

![img](https://s2.loli.net/2022/06/21/WJL5qmeDRPsvOrj.jpg) 

点击左侧开发者选项，选择右侧开发人员模式，系统会自动安装功能

![img](https://s2.loli.net/2022/06/21/c68YJlCsvzTIrk2.jpg) 

![img](https://s2.loli.net/2022/06/21/ZxoWi6EAjMISPlb.jpg) 

**§** ***\*常见问题\****

o 运行后不显示界面再次点击dock提示程序已运行或者启动就崩溃

原因：未安装VC2019运行库

下载下面链接程序DirectXRepair4.0然后解压

https://cloud.189.cn/t/6BfiaqfuEBNr

![img](https://s2.loli.net/2022/06/21/rxjL5a9cv7GpBFb.jpg) 

运行文件夹内对应的exe，然后按照下图所以依次点击，win7直接运行DirectX repair.exe，win8以上系统运行win8_win10.exe，【同时更新C++】是默认勾选的可以不用点击只是查看一下是否勾选就可以了，最后点击检测并修复然后重启系统，如果你是经常玩大型3A游戏基本是不用他修复的因为大型游戏必须有这些运行库才能玩

![img](https://s2.loli.net/2022/06/21/KekosX5EnJyfpNO.jpg)***\*Win7启动就崩溃或者无法运行和开启硬件加速方法：下载下面链接微软发布的功能更新补丁，\*******\*32位和64位下载对应你系统的32/64版本，安装完毕之后需要重启电脑\****

https://www.microsoft.com/zh-CN/download/details.aspx?id=36805

 

![img](https://s2.loli.net/2022/06/21/3o4HuQypfA5W8zT.jpg) 

下载慢的可以使用下面天翼云我已经下载好的

https://cloud.189.cn/t/MZJfuqNzMBVf

· 程序路径不要放在C盘，如果只有一个分区可以放在【C:\Users\你的用户名\AppData\Local】下建立一个MyDock文件夹，放在这里面就可以了。

· 开机无法启动

C++开机启动使用服务方式，在任务管理器中服务查看是否有MyDock服务

![img](https://s2.loli.net/2022/06/21/951BvzrLxIjqMpK.jpg) 

如果没有就打开dock设置重新勾选一次开机启动选项，如果还是没有mydock服务时***\*需要手动添加，管理员模式运行cmd\****

![img](https://s2.loli.net/2022/06/21/TZain3mCUOVwDlH.jpg) 

然后输入下面文字，binpath 替换为你的dock目录，第一exe文件是mydock.exe不能错，第二点等号后面有一个空格不能错是【start= auto】，第三路径要有引号

sc create MyDock displayname= MyDock start= auto binpath= “E:\Program Files (x86)\MyDock\MyDock.exe”

如果提示权限错误说明不是管理员模式运行

· MyDock最小化没有窗口动画

没有最小化动画分为两种情况

一、首先任务管理器查看有无dockmod(64).exe进程，然后查看dock最小化设置是否开启最小化动画如果没有dockmod(64).exe继续看，如果有直接看第二条

![img](https://s2.loli.net/2022/06/21/SKJpNR1hmzjWsZV.jpg) 

如果全部按照此设置依然没有dockmod进程需要手动在dock目录找到dockmod.exe右键管理员模式运行，如果依然不行打开任务计划程序进程手动修复，只是启动方式按照下图操作，win10系统打开搜索或者按WIN+S，搜索任务计划程序

![img](https://s2.loli.net/2022/06/21/GowCy9vRgQFD6n2.jpg) 

点击左侧任务计划程序库，查看中间是否有mydockmod计划任务，如果有双击mydockmod计划任务，如果没有点击右侧创建任务，然后下后面图例设置
![img](https://s2.loli.net/2022/06/21/sulTFGve1D8SQzM.jpg)

![img](https://s2.loli.net/2022/06/21/VNGEAjdr3XtqnBL.jpg) 

![img](https://s2.loli.net/2022/06/21/vUupakes1g9TomH.jpg) 

![img](https://s2.loli.net/2022/06/21/5xNdbkT6RqgVOf9.jpg) 

上面第二个图触发一定要留空，因为是dock启动以后从dock触发的dockmod启动不需要系统自己触发；启动程序的路径是你dockmod.exe的路径；如果是64位系统dockmod64也是这样操作。
二、任务管理器有dockmod(64).exe，先在dock偏好设置-最小化效果选择缩放效果

![img](https://s2.loli.net/2022/06/21/3THcpRtzmKrExDb.jpg) 

选择缩放效果后如果有最小化动画了，然后选择神奇效果等其他效果，后尝试勾选最小化使用GDI截图、***\*双显示器时拔掉第二屏、\****卸载显卡驱动（卸载的是dock最小化渲染使用显卡显示的那个显卡驱动）重新安装驱动此方法按照上面驱动篇操作

***\*双显卡双屏幕并且主屏集显输出第二屏独显输出\****时dock没有最小化动画只能用缩放效果

o 更新后出现如下提示

![img](https://s2.loli.net/2022/06/21/kld4MWzj25wIKrA.jpg) 

请到网站下载中心重新下载一次更新包替换文件即可

![img](https://s2.loli.net/2022/06/21/TdlsCcGoqQjKvfA.png) 

**§** ***\*报毒添加信任列表\****

如果dock、dockmod32位或者64位报毒可以添加排除项（***\*如果dockmod.exe运行中无故退出或者没有最小化动画也是被安全中心给杀了所以也要添加排序项\****），当然报毒问题最好是从我这里解决，主要是不知道那块代码给识别成病毒了，所以目前的办法只能手动添加。

开始菜单打开Windows安全中心，左侧点击病毒和威胁防护，右侧往下找到病毒和威胁防护设置，点击管理设置

![img](https://s2.loli.net/2022/06/21/ZmgFEULd2wsxIoV.jpg) 

然后往下找到排序项，点击添加或删除排除项，选择报毒dock(mod).exe即可，***\*最好是添加文件夹选择dock目录\****

![img](https://s2.loli.net/2022/06/21/lAeHxBDLzXmfE24.jpg) 

**§** ***\*添加天气图标崩溃\****

下载下面链接的高德天气城市代码

https://lbs.amap.com/api/webservice/download

![img](https://s2.loli.net/2022/06/21/gERDfOHP9KkYpQu.jpg) 

打开excel文件，搜索你的城市名称找到对应的代码，***\*adcode列就是天气城市代码，adcode是身份证的前六位数字也可以从adcode来查找自己的城市地区\****

![img](https://s2.loli.net/2022/06/21/ATP1kjJ59dwmhVl.jpg) 

然后打开dock目录中config.ini文件找到如下文字

[weather]

citycode=XXXXXX

cityname=XXXXXX

如果没有上面的文字手动复制放在config.ini内容的最底部，citycode=后面替换excel文件里面的城市代码，cityname=替换你的城市名称（城市名称可以随便填写支持Unicode文字）

**注意！！！如果excel文件内没有你的城市名字即找不到对应的城市代码就只能添加和你城市最近的城市代码，一定不要添加文件里面没有的城市代码否则崩溃无法启动！**

 
