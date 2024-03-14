# My learning process
2024Spring,Dian,Project-oriented

Day1 科学上网；
     注册github，创建git仓库并学习本地常用指令，链接本地仓库与github；
     安装linux虚拟机（RedHat，linux9.3），配置Linux系统；
     （被困很久的）将本机clash代理用在虚拟机的网络代理上，花费很长时间的主要原因是对linux虚拟机网络配置原理不熟悉，网上看到的各种方法细节上有所差别，最后看到几个思路相似的方法应用验证后解决了问题；
Day2 配置linuxC语言环境；

————————————————————————————————————————————————————————————————————————————
level 0-2
1.int getopt(int argc, char * const argv[],
                  const char *optstring)
char *optstring = "ab:c::"
单个字符a         表示选项a没有参数            格式：-a即可，不加参数
单字符加冒号b:     表示选项b有且必须加参数      格式：-b 100或-b100,但-b=100错
单字符加2冒号c::   表示选项c可以有，也可以无     格式：-c200，其它格式错误
