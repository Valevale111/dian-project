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
1.关于库函数 get_fps()"可变帧率"：
帧率：frames per second
2.decoder_init时参数加入视频地址后运行报错Segmentation fault (core dumped)
尝试使用gdb ./~ core查看崩溃原因定位；查看log文件；
/var/log/apport.log查看崩溃记录，查看core文件报错引导；
加入./libvideodecoder.a 后报错undefined reference to symbol 'avcodec_open2@@LIBAVCODEC_60'
3.rgb转灰度算法：
采用(0.2126 * red + 0.7152 * green + 0.0722 * blue)

