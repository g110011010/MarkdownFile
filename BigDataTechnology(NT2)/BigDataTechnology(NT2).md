---
title: 2017-9-26 
tags: 大数据,hudoop
author:sf
grammar_cjkRuby: true
---


## Course 1 大数据概述
### 1.7 海量数据并行处理技术的需求
1. 海量数据隐含着更准确的事实
	* 算法不再要紧，数据更重要！不再需
要研究复杂算法，找更多数据就行了
	* 大数据集上的简单算法能比小数据集上的复杂算法产生更好的结果

2. MapReduce是目前面向海量数据处理最为成功的技
术
### 1.8 并行处理技术MapReduce简介
1. MapReduce是Google公司发明的一种面向大规模海量数据处理的高性能并行计算平台和软件编程框架.
2. MapReduce是面向打过莫数据并行处理的
	* 基于集群的高性能并行计算平台:允许使用现在市场上的普通PC构造成包含三数千节点的分布式并行计算集群
	* 并行程序开发与运行框架
	* 并行程序设计模型和方法

3. 模仿Google MapReduce，基于Java设计出了称为Hadoop的开源MapReduce，该项目成为Apache下最重要项目

## Course 2 大数据平台Hadoop介绍
### 2.1 Hadoop简介
1. Hadoop是Apache旗下的一个开源分布计算平台
2. Hadoop是基于ＪＡＶＡ语言开发的,具有良好的跨平台性
3. Hadoop的核心是分布式文件系统HDFS(hadoop Distributed File System)和MapReduce

### 2.7 Hadoop项目结构
组件|功能
--|---|--
HDFS|分布式文件系统
MapReduce|分布式并行编程模型
YARN|资源管理和调度器
Tez|y运行在YARN之上的下一代Hadoop查询处理框架
Hive|Hadoop的数据仓库
HBase|Hadoop上的非关系型分布式数据库
1. Hadoop版本演变
	* v1.x 由数据存储和数据计算(集成了数据管理的功能)两个大部分组成
	* v2.x 由数据存储,数据管理(YARN系统),数据计算三个部分组成.增加了namenode HA 等特性

### 2.6 Hadoop各种版本


## Course 3 Hadoop系统安装运行

## Course 4 MapReduce简介
1. mapreduce处理大数据的思想：**分而治之**
2. 不可拆分的计算任务或相互间有依赖关系的数据无法进行并行计算。
3. **map**:对一组数据元素进行某种重复式的处理，获得中间结果
4. **reduce**：对Map的中间结果进行某种进一步的处理获得结果
5. 
## Chapter 5 分布式文件系统 HDFS
1. 分布式文件系统把文件分步存储在多个计算机结点上，成千上万的计算机结点构成计算机集群。
2. 分布式文件系统在牡蛎结构上是由计算机集群中多个结点构成的，这些结点分为两类，一类叫做==Master Node==，或者也被称为==名称结点（NameNode）==，另一类叫做==从结点（Slave Node）==或者也被称为==数据结点（DataNode）==
3. HDFS通过一定数量的数据复制保证数据存储的可靠性和出错恢复能力。
4. HDFS对顺序读取进行了优化，代价是随机访问的负载比较高
5. HDFS默认一个块的大小是64M，一个文件被分为多个块。
6. HDFS主要组件的功能：

NameNode|DataNode
--|---|--
存储元数据|存储文件内容
元数据保存在内存中|文件内容保存在磁盘
保存文件，block,datanode之间的映射关系|维护了block id 到datanode本地文件的映射关系。
