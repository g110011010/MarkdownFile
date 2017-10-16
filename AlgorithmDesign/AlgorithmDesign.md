---
title: 2017-9-25 
tags: 
author:sf
grammar_cjkRuby: true
---
<!--Teacher Info:-->
<!--email:lizhaoh888@bupt.edu.cn-->
<!--Tel:15810470206-->
<!--QQ:2457471851null-->
## Course2
### 2.1 蛮力法
1.依赖的基本技术:扫描

#### 2.1.1 组合问题中的蛮力法
 1. **0/1背包问题**:![enter description here][1]

### 2.2 任务分配问题
## Chapter 1 引言：某些典型的问题
### 1.1 第一个问题：稳定匹配
### 1.2 五个典型问题

## Chapter 2 算法分析基础
### 2.1 计算可解性
#### 2.1.1 定义效率的某些初步尝试 
#### 2.1.2 最坏情况运行时间与蛮力搜索
#### 2.1.3 多项式时间作为有效性的定义
1. 如果一个算法有多项式运行时间,则它是有效的
### 2.2 增长的渐进阶
### 2.3 用表和数组实现稳定匹配算法
### 2.4 一般运行时间的概述
### 2.5 更复杂的数据结构：优先队列


  [1]: https://www.github.com/g110011010/MarkdownFile/raw/master/StoryWriter/1507546270873.jpg
  
## Course 5
1. 二叉堆是一种特殊的堆，二叉堆是完全二元树（二叉树）或者是近似完全二元树（二叉树）。二叉堆有两种：最大堆和最小堆。最大堆：父结点的键值总是大于或等于任何一个子节点的键值；最小堆：父结点的键值总是小于或等于任何一个子节点的键值。

> 二叉堆一般用数组来表示。例如，根节点在数组中的位置是0，第n个位置的子节点分别在2n+1和 2n+2。因此，第0个位置的子节点在1和2，1的子节点在3和4。以此类推。这种存储方式便於寻找父节点和子节点。


2. 算法所消耗的时间主要取决于语句所重复的次数
3. 一个算法中所有语句的频度之和构成了该算法的运行时间。
4. 渐进时间复杂度：以基本语句（执行次数最多的一条语句）的频度作为复杂度衡量标准
5. 插入排序 快速排序，时间复杂度
6. <p>常用的排序算法的时间复杂度和空间复杂度</p>
<div class="xspace-itemmessage">
<p>
<table style="width: 587px; height: 1px;" border="1">
<tbody>
<tr>
<td width="587" height="37" valign="middle">
<p align="center"><span>排序法 </span></p>
</td>
<td width="587" height="37"><span>最差时间分析</span></td>
<td width="587" height="37"><span>平均时间复杂度 </span></td>
<td width="587" height="37"><span style="color: #555555;">稳定度 </span></td>
<td width="587" height="37"><span style="color: #555555;">空间复杂度 </span></td>
</tr>
<tr>
<td width="587" height="42" align="center"><span>冒泡排序</span></td>
<td width="587" height="42" align="center"><span>O(n<sup>2</sup>)</span></td>
<td width="587" height="42" align="center"><span style="color: #555555;">O(n<sup>2</sup>) </span></td>
<td width="587" height="42" align="center"><span style="color: #555555;">稳定 </span></td>
<td width="587" height="42" align="center"><span style="color: #555555;">O(1) </span></td>
</tr>
<tr>
<td width="587" height="39" align="center"><span>快速排序</span></td>
<td width="587" height="39" align="center"><span>O(n<sup>2</sup>)</span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(n*log<sub>2</sub>n) </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">不稳定 </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(log<sub>2</sub>n)~O(n) </span></td>
</tr>
<tr>
<td width="587" height="39" align="center"><span>选择排序</span></td>
<td width="587" height="39" align="center"><span>O(n<sup>2</sup>)</span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(n<sup>2</sup>) </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">稳定 </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(1) </span></td>
</tr>
<tr>
<td width="587" height="39" align="center"><span>二叉树排序</span></td>
<td width="587" height="39" align="center"><span>O(n<sup>2</sup>)</span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(n*log<sub>2</sub>n) </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">不一顶 </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(n) </span></td>
</tr>
<tr>
<td width="587" height="39" align="center">
<p align="center"><span>插入排序 </span></p>
</td>
<td width="587" height="39" align="center"><span>O(n<sup>2</sup>)</span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(n<sup>2</sup>) </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">稳定 </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(1) </span></td>
</tr>
<tr>
<td width="587" height="39" align="center"><span>堆排序</span></td>
<td width="587" height="39" align="center"><span>O(n*log<sub>2</sub>n) </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(n*log<sub>2</sub>n) </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">不稳定 </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(1) </span></td>
</tr>
<tr>
<td width="587" height="39" align="center"><span>希尔排序</span></td>
<td width="587" height="39" align="center"><span>O</span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">不稳定 </span></td>
<td width="587" height="39" align="center"><span style="color: #555555;">O(1)</span></td>
</tr>
</tbody>
</table>
</p>
6. 大O符号 常数级（O(1)）eg:查找一个数组中的第一项 ; 对数级（（O（log n））） 线性级 多项式级 （以上为多项式时间复杂度的算法 以下为指数时间的算法） 指数集 阶乘级
7. 大Ω符号：确定算法复杂度的下线
8.  非递归算法分析：首先找到基本语句
9.  算法的后验分析