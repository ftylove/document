###lsof order

```
lsof 命令用于查看进程打开的文件，打开的文件进程，进程打开的端口(TCP,UDP)。找回/恢复删除的
文件。是十分方便的系统监视工具，因为lsof命令需要访问核心和各种文件，所以需要root用户执行。

在linux环境下，任何事物都以文件的形式存在，通过文件不仅仅可以访问常规数据，还可以访问网络
连接和硬件。所以如传输控制协议(TCP)和用户数据报协议(UDP)套接字等，系统在后台都为该程序分配
了一个文件描述符，无论这个文件的本质如何，该文件描述符为应用程序与基础操作系统之间的交互提
供了通用接口。因为应用程序打开文件的描述符列表提供了大量关于这个应用程序本身的信息，因此通
过lsof工具能够查看这个列表对系统监测以及排错将是很有帮助的。

####语法
> lsof(选项)

> -a: 列出打开文件的进程;
> -c<进程名>: 列出制定进程所打开的文件;
> -g: 列出GID号进程详情;
> -d<文件号>: 列出占用该文件号的进程;
> +d<目录>: 列出目录下被打开的文件;
> +D<目录>: 递归列出目录下被打开的文件;
> -n<目录>: 列出使用NFS的文件;
> -i<条件>: 列出符合条件的进程;(4、6、协议、端口、@ip)
> -p<进程号>: 列出指定进程号所打开的文件;
> -u: 列出UID号进程的详情;
> -h: 显示帮助信息;
> -v: 显示版本信息;

####实例
lsof
COMMAND     PID  TID    USER   FD      TYPE             DEVICE  SIZE/OFF       NODE NAME
systemd       1         root  cwd       DIR              253,1      4096        128 /
systemd       1         root  rtd       DIR              253,1      4096        128 /
systemd       1         root  txt       REG              253,1   1214408   67353642 /usr/lib/systemd/systemd
systemd       1         root  mem       REG              253,1     58288  134296371 /usr/lib64/libnss_files-2.17.so
systemd       1         root  mem       REG              253,1     90632  134396203 /usr/lib64/libz.so.1.2.7
systemd       1         root  mem       REG              253,1     19888  134396318 /usr/lib64/libattr.so.1.1.0
systemd       1         root  mem       REG              253,1    113320  134296363 /usr/lib64/libnsl-2.17.so
systemd       1         root  mem       REG              253,1    153184  134359131 /usr/lib64/liblzma.so.5.0.99
systemd       1         root  mem       REG              253,1    398264  134396152 /usr/lib64/libpcre.so.1.2.0
systemd       1         root  mem       REG              253,1     19512  134296359 /usr/lib64/libdl-2.17.so
systemd       1         root  mem       REG              253,1   2107768  134296353 /usr/lib64/libc-2.17.so
systemd       1         root  mem       REG              253,1    141616  134296379 /usr/lib64/libpthread-2.17.so
systemd       1         root  mem       REG              253,1     88720  134294664 /usr/lib64/libgcc_s-4.8.2-20140120.so.1
systemd       1         root  mem       REG              253,1    304536  134396216 /usr/lib64/libdbus-1.so.3.7.4
systemd       1         root  mem       REG              253,1     44048  134296383 /usr/lib64/librt-2.17.so
systemd       1         root  mem       REG              253,1     91520  134396862 /usr/lib64/libkmod.so.2.2.4

FD: 文件描述符
```



