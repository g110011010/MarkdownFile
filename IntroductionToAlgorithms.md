---
title: 2017-10-8未命名文件 
tags: 算法导论,第三版,自学,笔记
grammar_cjkRuby: true
Teacher info:
name:
email:
tel:
---
## Chapter 1 算法在计算中的作用
### 1.1 算法
1. ==算法（Algorithm）==：非形式的说,算法就是任何良定义的计算过程，该过程取某个值或者值的集合作为**输入**并产生某个值或值的集合作为**输出**。
2. ==数据结构==：数据结构是一种存储和组织数据的形式，旨在便于访问和修改
### 1.2 作为一种技术的算法
1. 计算机是很快的但还不是无限快。存储器是廉价的但不是免费的。算法的最主要作用就在时间或者空间方面有效的利用资源来解决问题。
## Chapter 2 算法基础
### 2.1 插入排序
#### 2.1.1 算法原理
1. ![enter description here][1]
2. ![enter description here][2]

#### 2.1.2 循环不变式
1. 循环不变式主要用来帮助理解算法的正确性。
2. 循环不变式必须证明三条性质：

	* **初始化**：循环的第一次迭代之前它为真
	* **保持**：如果循环某次迭代之前它为真，那么下次迭代之前它仍然为真。
	* **终止**:在循环终止时，不变式为我们提供一个有用的性质，该性质有助于证明算法是正确的。
#### 2.1.3 编程实现
1. C++

``` C++
#include<iostream>
#include<string>
using std::cin;
using std::cout;
using std::endl;
int main(){
    int num_a[]={12,3,23,12,453,231,3,2345,32};
    int num_a_lenght=9;
    for(int i=1;i<num_a_lenght;i++){
         int tem=num_a[i];
         int j=i;
         while(num_a[j-1]>tem&&j>0){
            num_a[j]=num_a[j-1];
            j--;
         }
         num_a[j]=tem;
    }
    for(int i=0;i<num_a_lenght;i++){
        cout<<num_a[i]<<endl;
    }
    return 0;
}
```


### 2.2 分析算法
### 2.3 设计算法
#### 2.3.1 分治法
#### 2.3.2 分析分治算法
## Chapter 3 函数的增长
### 3.1 渐进符号
### 3.2 标准记号与常用函数


  [1]: ./images/1507510897781.jpg
  [2]: ./images/1507510941403.jpg