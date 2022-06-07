# 数学建模导论：基于python语言（2022秋）

#### 介绍
本实验是《数学建模导论：基于Python语言》的配套实验内容，马马将在这次实验中带大家一步步从小白到竞赛实战，让数学建模不再是一项可怕的竞赛。

![输入图片说明](%E5%B0%81%E9%9D%A2.png)

## Python环境的安装
在开始实验之前，大家可以先去anaconda官网安装python大礼包：www.anaconda.com

当然如果想安装原生Python也可以直接上python官网：www.python.org

但是Python如果是原生状态下的话里面啥都没有，所以如果碰到了库不存在的话，将命令行打开，键入pip install xxxx 能够解决大多数问题。
不过我想应该没有什么同学愿意为了节约一点表面上的空间去安装原生Python吧，不会吧不会吧？一如你去集贸的呷哺呷哺吃火锅你难道只会点一个锅底不点菜的吗？
anaconda实际上就是提供锅底的同时还会提供你毛肚、鸭血、鸭肠等。所以，为什么不去安装一个anaconda呢？

如果觉得编程环境不好用的话可以加装一个VSCode或者Pycharm，但是华科的学生装正版Pycharm可能还有一点点问题因为学校邮箱出了点事。

## 实验一：Python的基础语法

本次实验的基本目的是熟悉Python的基础语法。首先我们可以打开命令行（windows用户可以在cortana中键入cmd，会弹出命令提示符），然后键入python回车就可以切换到python命令行模式了。这一模式下我们可以试试它的hello world和C的hello world有多大差距：

![输入图片说明](image.png)

可以看到Python的hello world仅需要一行。但是在更多情况下，我们和C一样会在文本文件中写程序然后运行。

这一次实验我们的目的就是熟悉基本的控制流和集合等内容。

### 1. 熟悉Python的输入输出操作，并实现对一个输入序列的冒泡排序
现在对计算机1915班的前五名同学模电成绩想排个序，要求：

- 输入成绩个数为5，用input()函数实现
- 将输入的五个数保存成列表，并进行冒泡排序
- 不允许使用list自带的sort()方法，必须自己设置冒泡排序
- 将五个数排序后的结果排成一行输出到控制台

### 2. 分支语句判断
现在马马考完了模电，老师想在控制台里面根据我的成绩评价我的学习水平，要求：

- 控制台输入马马的模电分数
- 如果分数高于95，输出“马马+是卷王”；如果在80-95之间，输出“马马+牛牛”；如果在60-80之间，输出“马马+摆烂了”；如果低于60，输出“马马+老师，你不会又得重修了吧”
- 异常处理：如果分数是一个小于零的数或者输入的根本就不是数字如何handle？

### 3. 循环语句
老师手里有一份光之国模电考试的成绩单，保存成了txt文件，每一行分别是班里同学的名字和分数。现在需要：

- 利用open和read函数循环读取每一行，将结果保存到字典中
- 首先输出杰克、雷欧和贝利亚的模电成绩，如果检索不到人名需要报警“找不到这位同学”
- 然后循环遍历这个字典，对于每个同学的模电成绩按照第二关中的操作输出这位同学的状态

### 4. 函数编写
试着将第三关的语句改写为一个函数，函数参数为成绩单文件的路径与文件名。


## 实验二：Python规划求解

本次实验的目的是为了熟悉基本的规划问题求解策略。求解规划问题需要用到numpy和scipy库，这两个库我建议先去熟悉一些基本操作会比较好。

这里我附上numpy和scipy的官方文档：

numpy官方文档：https://numpy.org/

scipy官方文档：https://scipy.org/

主要的方法就在scipy.optimize库当中，包括minimize、linear_sum_assignment等方法。

### 1. 线性规划问题求解

求这样一个线性规划的最优解：
![img]([http://latex.codecogs.com/gif.latex?\\ \min_x f=2x_1+3x_2-x_3\\s.t.\begin{cases}x_1+x_2+3x_3\leq 100\\-2x_2+x_3\ge 15\\3x_1-x_2-4x_3\ge -20\\x_1+x_2+x_3=70\\x_1,x_2,x_3\ge 0\end{cases}](https://latex.codecogs.com/svg.image?\min_x&space;f=2x_1&plus;3x_2-x_3\\s.t.\begin{cases}x_1&plus;x_2&plus;3x_3\leq&space;100\\-2x_2&plus;x_3\ge&space;15\\3x_1-x_2-4x_3\ge&space;-20\\x_1&plus;x_2&plus;x_3=70\\x_1,x_2,x_3\ge&space;0\end{cases}))

### 2. 非线性规划问题求解

求这样一个非线性规划的最优解，要求使用scipy.optimize.minimize求解：
![img]([http://latex.codecogs.com/gif.latex?\\ \min_x f=x_1^2+3x_2^2-x_1x_3\\s.t.\begin{cases}x_1+x_2+3x_3\leq 100\\-2x_2+x_3\ge 15\\x_1+x_2+x_3=70\\x_1^2+x_2^2\leq 400\\x_1,x_2,x_3\ge 0\end{cases}](https://latex.codecogs.com/svg.image?\min_x&space;f=x_1^2&plus;3x_2^2-x_1x_3\\s.t.\begin{cases}x_1&plus;x_2&plus;3x_3\leq&space;100\\-2x_2&plus;x_3\ge&space;15\\x_1&plus;x_2&plus;x_3=70\\x_1^2&plus;x_2^2\leq&space;400\\x_1,x_2,x_3\ge&space;0\end{cases}))

### 3. 指派问题求解
现在光之国的五位奥特曼与阿布索留特族的五个小金人开始了1v1的车轮战，如果你现在安排奥特兄弟与他们1v1的战斗，每一项代表一个奥解决一个小金人所需要的时间。只有在最短的时间内打败所有小金人才能救出尤莉安公主。请问对于给定的小金人ABCDE，应该按照怎样的战斗策略使得五场战斗的时间总和最短？

| 奥特曼 | A    | B    | C    | D    | E    |
| ------ | ---- | ---- | ---- | ---- | ---- |
| 佐菲   | 22   | 16   | 20   | 35   | 18   |
| 初代   | 20   | 12   | 35   | 40   | 26   |
| 赛文   | 11   | 19   | 15   | 17   | 21   |
| 杰克   | 25   | 30   | 21   | 37   | 40   |
| 艾斯   | 22   | 26   | 35   | 30   | 19   |

### 4. 综合建模
原题的链接附上：https://blog.csdn.net/OK_XIAOCHEN/article/details/124523838?utm_term=matlab%E4%B8%AD%E7%9A%84%E6%8C%87%E6%B4%BE%E9%97%AE%E9%A2%98&utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~sobaiduweb~default-0-124523838-null-null&spm=3001.4430

现在光之国开通了从M78星云（A）到L77星云（B）和U40（C）星云的宇宙航线，这些航线每天班次起飞与到达时间如下表。 设飞船在机场停留的损失费用大致与停留时间的平方成正比. 又每架飞船从降落到下班起飞至少需 2 小时准备时间， 试决定一个使停留费用损失为最小的分配飞行方案。

![image](https://user-images.githubusercontent.com/61874427/172405114-de0bd77a-416d-4836-913b-635d27573470.png)

到M78星云损失费用：

![img](https://img-blog.csdnimg.cn/7c421911268f43b1a17a5126430bd535.png)

到L77星云损失费用：

![image](https://img-blog.csdnimg.cn/7c421911268f43b1a17a5126430bd535.png)

到U40星云损失费用：

![image](https://img-blog.csdnimg.cn/68617b292cf34e79a0da7db521ccc6ca.png)

对于问题四，写出你的分析思路，建立的模型表达式，程序和求解结果。最终形成一个不超过两页A4纸的文档。没啥格式要求，你认为你将你的思路表达清楚就够了。

## 实验三：Python微分方程建模

## 实验四：鸢尾花的数据预处理与可视化

## 实验五：产品的多维度评价

## 实验六：比特币价格预测

## 实验七：最短路径问题

## 实验八：量化投资选股问题

## 实验九：鸢尾花的分类与聚类

## 实验十： 波士顿房价预测

## 实验十一：34城市的TSP问题

## 实验十二：关联关系挖掘
