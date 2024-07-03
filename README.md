# -
大数据开发学习
1.第一天 软件的安装跟Java的学习
(1)notepad~~ 替换notebook++
(2)pycharm安装python库，打开命令行，先安装pip，输入命令：python -m ensurepip --default-pip 
再安装所需要的库+某个特定地址：pip install --trusted-host cmc-cd-mirror.rnd.huawei.com -i http://cmc-cd-mirror.rnd.huawei.com/pypi/simple
2.
Hadoop 优势：高效、可靠、可拓展、可容错
Hadoop 组成：MapReduce(计算)、Yarn（资源调度）、HDFS（数据存储）

3.1 HDFS
HDFS不适合低延时的数据访问，做离线比较好
HDFS的文件是分块储存的，不能设置太大也不能太小，主要取决于磁盘的传输速率
HDFS与Shell ，主要用于启动 上传本地文件拷贝到HDFS、
面试重点：
HDFS的写数据流程：1.客户端像Name Node请求上传文件---》Name Node检查响应客户端可以上传---》客户端请求上传第一个block，请返回DaraNode---》返回dn1\dn2等节点，表示采用这三个节点储存---》客户端传输数据完成












 

  
