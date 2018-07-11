
# Android dumpsys Meminfo Summary 

##What is dumpsys ?

- dumpsys 是一个在 Android 上运行的命令行工具，它提供有关系统服务的信息。
- dumpsys 是一个bin 文件，在系统的位置 system/bin/dumpsys
- dumpsys 可以通过 'adb  shell dumpsys' 来运行(PC连接手机)

## dumpsys usage info
>> 
       dumpsys [-t TIMEOUT] [--help | -l | --skip SERVICES | SERVICE [ARGS]]
       
         --help: shows this help
         
         -l: only list services, do not dump them
         
         -t TIMEOUT: TIMEOUT to use in seconds instead of default 10 seconds
         
         --skip SERVICES: dumps all services but SERVICES (comma-separated list)
         
         SERVICE [ARGS]: dumps only service SERVICE, optionally passing ARGS to it

## dumpsys 常用命令 

dumpsys 可以 dump 的 系统服务非常多, 可以用 dumpsys -l 列举出来，在我Android 8.1 的设备上， dumpsys -l 结果有个140多个。

常用的命令是 dumpsys meminfo 查看内存使用信息，以及 dumpsys SurfaceFlinger 查看 Surface 和 Layer 相关信息。这里主要讨论 dumpsys meminfo。 


## dumpsys meminfo with args 







