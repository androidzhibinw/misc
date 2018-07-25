
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

dumpsys meminfo 可以带参数 pid 或者 process name , dump 一个进程的 meminfo .

比如： adb shell dumpsys meminfo com.netease.AVALON  结果如下： 

>>

    Applications Memory Usage (in Kilobytes):
    Uptime: 82497083 Realtime: 82497083
    
    ** MEMINFO in pid 4736 [com.netease.AVALON] **
                       Pss  Private  Private  SwapPss     Heap     Heap     Heap
                     Total    Dirty    Clean    Dirty     Size    Alloc     Free
                    ------   ------   ------   ------   ------   ------   ------
      Native Heap    95253    95176        0      198   110080   102036     8043
      Dalvik Heap    24676    24648        0      118    32791    16396    16395
     Dalvik Other     1331     1328        0        4
            Stack       36       36        0        8
           Ashmem      134      128        0        0
          Gfx dev    14784    14712       72        0
        Other dev        8        0        8        0
         .so mmap    49248    42612     2088      141
        .apk mmap     1965       56       64        0
        .ttf mmap       12        0        0        0
        .dex mmap     6072       12     2232        0
        .oat mmap     4475        0     1056        0
        .art mmap     1647      684       24        9
       Other mmap      413        4       56        0
       EGL mtrack    98460    98460        0        0
        GL mtrack    82284    82284        0        0
          Unknown    19669    19664        0      210
            TOTAL   401155   379804     5600      688   142871   118432    24438
    
     App Summary
                           Pss(KB)
                            ------
               Java Heap:    25356
             Native Heap:    95176
                    Code:    48120
                   Stack:       36
                Graphics:   195528
           Private Other:    21188
                  System:    15751
    
                   TOTAL:   401155       TOTAL SWAP PSS:      688
    
     Objects
                   Views:       14         ViewRootImpl:        1
             AppContexts:        4           Activities:        1
                  Assets:        3        AssetManagers:        4
           Local Binders:       19        Proxy Binders:       22
           Parcel memory:        9         Parcel count:       39
        Death Recipients:        2      OpenSSL Sockets:        8
                WebViews:        0
    
     SQL
             MEMORY_USED:        0
      PAGECACHE_OVERFLOW:        0          MALLOC_SIZE:        0

在Linux 下




