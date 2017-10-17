---
title: 2017-9-26 
tags: 大数据,hudoop
author:sf
grammar_cjkRuby: true
---


## Course 1 大数据概述
### 1.8 并行处理技术MapReduce简介
1. MapReduce是Google公司发明的一种面向大规模海量数据处理的高性能并行计算平台和软件编程框架.
2. MapReduce是面向打过莫数据并行处理的

	* 基于集群的高性能并行计算平台:允许使用现在市场上的普通PC构造成包含三数千节点的分布式并行计算集群
	* 并行程序开发与运行框架
	* 并行程序设计模型和方法

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


## 第三章 Hadoop系统安装运行


## Chapter 5 
### 1
#### 1.2 HDFS基本特征
1. HDFS对顺序读写进行了优化.支持大量数据的快速顺序读出,代价是对随机访问的访问负债较高
2.  