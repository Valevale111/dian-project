# My learning process
2024Spring,Dian,Project-oriented

Day1 科学上网；
     注册github，创建git仓库并学习本地常用指令，链接本地仓库与github；
     安装linux虚拟机（RedHat，linux9.3），配置Linux系统；
     （被困很久的）将本机clash代理用在虚拟机的网络代理上，花费很长时间的主要原因是对linux虚拟机网络配置原理不熟悉，网上看到的各种方法细节上有所差别，最后看到几个思路相似的方法应用验证后解决了问题；
Day2 配置linuxC语言环境；

————————————————————————————————————————————————————————————————————————————
level 0
（0-2）
1.int getopt(int argc, char * const argv[],
                  const char *optstring)
char *optstring = "ab:c::"
单个字符a         表示选项a没有参数；单字符加冒号b:     表示选项b有且必须加参数；单字符加2冒号c::   表示选项c可以有，也可以无

命令行选项解析函数(C语言)：getopt()和getopt_long() - 肖邦linux - 博客园
https://www.cnblogs.com/liwei0526vip/p/4873111.html
www.cnblogs.com
（0-3）
2.linux 下的 .a(静态库) 文件 .so（动态库） 文件
静态链接的可执行文件要比动态链接的可执行文件要大得多，因为它将需要用到的代码从二进制文件中“拷贝”了一份，而动态库仅仅是复制了一些重定位和符号表信息;

浅谈静态库和动态库 - 知乎
https://zhuanlan.zhihu.com/p/71372182
zhuanlan.zhihu.com
注：编译时链接库；也需要#include库；

level 1
（1-1）
1.关于库函数 get_fps()"帧率"：
帧率：frames per second
2.decoder_init时参数加入视频地址后运行报错Segmentation fault (core dumped)
尝试使用gdb ./~ core查看崩溃原因定位；查看log文件；
/var/log/apport.log查看崩溃记录，查看core文件报错引导；
加入./libvideodecoder.a 后报错undefined reference to symbol 'avcodec_open2@@LIBAVCODEC_60'
3.rgb转灰度算法：
采用0.299 * r + 0.587 * g + 0.114 * b
（1-2）resize函数
1.在c工程中，源文件中要包含自己的头文件；
//2.由于RGB图像对应R、G、B三个通道的数据，故而不能直接池化，需要先进行卷积，再用之后得到的数据进行池化；
2.对RGB图像，采取：            // 遍历窗口内的像素,通过比较窗口内元素的灰度值
            //找到灰度值最大的像素，作为当前窗口内最具代表性的颜色值，保存索引
            //根据其打印彩色字符

level 2
(2-1)
1.多线程编程；进程和线程
·一个进程可以有一个或多个线程，各个线程之间共享程序的内存空间(也就是所在进程的内存空间，不包括栈)。一个标准的线程由线程ID、当前指令指针(PC)、寄存器和堆栈组成。而进程由内存空间(代码、数据、进程空间、打开的文件)和一个或多个线程组成。
·互斥锁机制和信号量机制：
（n=1:互斥锁，eg.生产者消费者模型）通过访问时对共享资源加锁的方法，防止多个线程同时访问共享资源。锁有两种状态：未上锁和已上锁。在访问共享资源时，进行上锁，在访问结束后，进行解锁。若在访问时，共享资源已被其它线程锁住了，则进入堵塞状态等待该线程释放锁再继续下一步的执行。这种锁我们称为互斥锁。
（n>=1:信号量机制）



