+++
title = "车间调度问题(JSP)的解决方法"
date = 2018-05-19
draft = false
summary = "运筹学大作业使用车间调度问题，总结一下几种解决方法"

tags = ["Operations"]
categories = ["JSP","linear programming"]

[header]
image = ""
caption = ""
preview = true

+++

>[运筹学的大作业](/pdf/Project.pdf)要求解决一个车间调度问题(JSP)，这里列举一下几种解决方案

### 车间调度问题(JSP)

这部分的介绍可以参看[车间作业调度](https://wenku.baidu.com/view/1fc939aef524ccbff12184dc.html)以及[车间调度问题综述](/pdf/作业车间调度问题综述.pdf)。

单车间调度问题（Job-shop scheduling problem, JSP）是最基本、最著名的调度问题，也是NP难问题，无最优解精确算法。

#### 一般类型的JSP问题
n个工件在m台机器上加工，每个工件有特定的加工工艺，每个工件加工的顺序及每道工序所花时间给定，安排工件在每台机器上工件的加工顺序，使得某种指标最优。

#### 题设
不同工件的工序之间无顺序约束；
工序开始则不能间断，每个机器在同一时刻只能加工一个工序；
机器不发生故障。
调度的目标就是确定每个机器上工序的加工顺序和每个工序的开工时间，使最大完工时间(makespan)最小或其他指标达到最优。JSP调度问题简明表示为$n/m/G/C_{max}$。

#### 问题分支
在本次大作业中，一共有三个问题，其中1问题是流水作业调度问题(FSSP)，指的是所有的工件具有相同的加工工序，2问题是柔性作业车间调度问题(FJSP)，突破了资源唯一性的限制，3问题是通常意义上的车间调度问题(JSSP)。

### 车间调度问题的解决方法

#### 整数规划法

$n/m/G/C_{max}$问题的常用数学描述：

$$Min~max(max~c_{ik})$$

$$s.t.~ c_ {ik}-p_ {ik}+M(1-a_ {ihk}) > c_ {ih},i=1,2,..,n~h,k = 1,2,...,m$$

$$c_ {jk}-c_ {ik}+M(1-x_ {ijk})>p_ {jk}$$

$$c_{ik}>0,i=1,2,..,n,k=1,2,...,m$$

$$x_{ijk}=0或1~i,j=1,2,...,n~k=1,2,...,m$$

其中目标函数即为Makespan，约束条件表示各个工艺约束条件决定的工件的各个操作的先后加工顺序以及加工各个工件自己的先后顺序，式子中$c_ {ik}$和$p_ {ik}$分别表示i工件在机器k上的完成时间以及加工时间，M是一个足够大的正数，$a_ {ihk}$和$x_ {ijk}$分别表示指示系数以及指示变量，最终意义为：

机器h先于机器k加工工件i则$a_ {ihk} = 1$，否则$a_ {ihk} = 0$。
工件i先于工件j在机器k上加工，则$x_ {ijk} = 1$，否则$x_ {ijk} = 0$。

#### 帕累托最优路径方法

**帕累托最优路径：**

对于求解极小值的多目标问题(各个工件的完工时间达到极小)，称到达状态$x_ a$的路径$P_ a^j$为帕累托最优路径，当路径$P_ a^j$的各个工件的完工时间不超过其余的任意一条路径$P_ a^k$的对应的各个工件的完工时间。$v^r(P_ a^j)<=v^r(P_ a^k)$对于路径涉及到的所有资源r均成立，而且至少有一个严格的不等式成立。

R1的完工时间的帕累托最优路径就是整个调度过程所需的最少的时间。

>在不损害任何一个工件的最终完成时间的前提下，无法改善某个工件的最终完成时间。但这个概念真的是全局最优的吗？表示怀疑.....待研究
