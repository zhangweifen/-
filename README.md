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

lateral view 炸裂函数，可以将一个数组分割成多行
LATERAL VIEW 允许你在一个查询中，对于每一行输入数据，生成多行输出数据
explode 是一个表生成函数（TGF），用于将数组或映射（map）列中的元素转换为一行行的形式 
explode(cates) 会将cates数组中的每个元素转换为一行
LATERAL VIEW explode(cates) tmp AS cate 的意思是：对于原始表中的每一行，将cates数组列中的每个元素都转换为一行，并将这些元素的值放在名为cate的新列中。然后，你可以像引用普通表一样引用这个tmp临时表
![image](https://github.com/zhangweifen/-/assets/45863647/89db5650-2be2-4ec4-8ce9-9d4fa00ec94d)
![image](https://github.com/zhangweifen/-/assets/45863647/a7fe0c25-e908-496d-ab27-788e38aef73d)

累加函数！分组累加，可以sum avg
ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW 定义的窗口范围是从结果集的开始位置到当前行，即包含当前行及其之前的所有行




三、实操
1.先需求调研-数据接入（数据表授予）-数据探索跟环境数据同步-指标建模跟数据建模
2.任务开发跟编排-离线 实时数据开发-数据评估与验证-发布部署-数据集成（这里有一个数据集成的概念）
》》数据集成（如果是涉及到隐私或者敏感数据，需要数据评审，走流程审批）
tips:sql类的可以在平台在线开发，通过审批后在生产环境上线，如果是Java Python开发的，需要在另一个平台开发审核再上线（软件包是否开源，能否使用）
3.数据开发跟运维：数据/任务及时日落管理，做到资源成本管控。
3.1 日落类型：（1）数据表：对test表、重复数据表、不规范命名表、低价值数据等；
（2）对临时任务、低效任务、刷新任务、初始化任务日落
（3）不再使用、调整的数据域日落
（4）低访问的报表、自助分析、标签等日落
-----------数据分析师-----------
4.自助分析（数据分析师）
4.1 标签开发：
（1）标签需求分析-标签口径试算-标签开发/隐私评审
（2）（数据工程师做）规则标签开发
（3）标签发布
全过程最好再平台上操作，并且谁开发谁负责，涉及到用户隐私。











 

  
