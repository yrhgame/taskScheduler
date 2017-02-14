# Win7设置任务计划程序

Win7设置定时任务，执行本地php任务程序

- 创建BAT批处理程序
- 创建任务计划程序


### 1、创建BAT批处理程序

<pre><code>
@echo off
start iexplore.exe http://www.test.com/index.php
ping -n 10 127.0.0.1>nul
taskkill /f /im iexplore.exe
exit
</code></pre>

以上代码存储为 E:/task/case.bat

### 2、创建任务计划程序

* 打开任务计划程序
* 创建任务 - 输入任务名称
* 特别注意在：常规 - 安全选项 - 更改用户->设置为SYSTEM 【使用最高权限运行】
* 新建触发器，设置任务定时规则
* 新建操作，设置为【启动程序】，【程序或脚本】选中步骤1中的case.bat路径(E:/task/case.bat)，注意【起始于(可选)】必须填case.bat所在路径(E:\task\）


按以上步骤即可实现 Win7定时计划任务
