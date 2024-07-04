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
 HDFS的写数据流程：1.客户端像Name Node请求上传文件---》2.Name Node检查响应客户端可以上传---》3.客户端请求上传第一个block，请返回DaraNode---》4.返回dn1\dn2等节点，表示采用这三个节点储存---》5.客户端请求建立节点通道---》6.3个应答成功---》7.传输数据---》8.客户端传输数据完成
 后面的block不断重复3-8这个过程
！HDFS的数据跟hive的元数据区别：hive的元数据存储的是表名、库名、表结构等信息，hdfs是元数据查询跟记录状态，相当于，hive的元数据是hdfs数据映射出来的表结构
！！hdfs是数据，hive是数据的数据
3.2 hive 语法重点！
（1）CREATE [TEMPORARY] [EXTERNAL] TABLE [IF NOT EXISTS]  创建临时外部表 TEMPORARY临时  EXTERNAL 外部
（2）PARTITIONED BY（重点）
创建分区表
（3）CLUSTERED BY ... SORTED BY...INTO ... BUCKETS（重点）
创建分桶表
（4）ROW FORMAT（重点）
指定SERDE，SERDE是Serializer and Deserializer的简写。
ROW FORAMT DELIMITED 表示 文件中的每个字段按照特定分割符进行分割
FIELDS TERMINATED BY '\t' 字段以制表符分隔 通常是处理txt文件
ROW FORAMT DELIMITED FIELDS TERMINATED BY '\t' 表示 这个Hive表的行格式是分隔符格式的，并且字段之间是由制表符分隔的











 

  
