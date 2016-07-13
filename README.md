# mathexamgen
MathExamGen：科学快速的生成中学数学试卷（Matlab+Texlive）. 大体思路就是利用Matlab科学的整合数学题库中的题目，然后生成相应的tex文件，最后借助自带的xelatex编译器编译成pdf文件。

## 1. bhcexam 安装

windows 下的安装方法

```
tlmgr bhcexam 
```

如果安装不了，可以使用项目附带的`BHCexam.cls`和`BHCexam.cfg`. 


项目介绍：

### 2. 数学题库

存储类型：csv或者数据库
变量列表：

|变量|变量名|描述|取值|
| ---- |:----:| :---:|:---|
|1| ID| 题目编号| 6位数字 |
|2|qtype| 题目类型|1代表填空题，2代表选择题等|
|3|question| 题目内容| 题目的latex代码|
|4|options| 题目相关信息|选择题的四个选项等信息|
|5|answer| 题目答案| |
|6| topic| 题目的考点| 分级考点，如：高二-数列-递推|

### 3.主要思路

结合Matlab的数据处理与分析功能，我们可以做很多事，例如

1. 根据给定的类型要求和考点要求，随机生成一张试卷；
2. 结合单个同学的历史数据，生成适合他/她的试卷，在这份试卷中易错点出现的频次更高一些；
3. 由于所有试卷都是生成的，我们可以更科学快捷的评估单次考试。

