Table of Contents
=================

- [WHU-ACM-OJ 题意](#whu-acm-oj-题意)
  - [编写规范](#编写规范)
  - [5 Holding Animals (3pts)](#5-holding-animals-3pts)
  - [6 Language of Animals (3pts)](#6-language-of-animals-3pts)
  - [7 Feeding Animals I (1pts)](#7-feeding-animals-i-1pts)
  - [8 Feeding Animals II (3pts)](#8-feeding-animals-ii-3pts)
  - [10 Alternate Sum (3pts)](#10-alternate-sum-3pts)

# WHU-ACM-OJ 题意

## 编写规范

1. 保持题号升序, 在对应位置插入
2. 题目名称使用 h2 标题 (两个 #), 格式为 `("## %d %s (%dpts)", 题号, 题名, 分数)`
3. 记得更新目录 (Table of Contents), 目录格式参考[这里](https://github.com/ekalinin/github-markdown-toc.go#remote-files)或下文说明
4. 写明输入输出格式. 能让人在不看网站上漫长的英文题面的情况下, 直接开始 coding
5. 标注数据范围, 除非原题就没写
6. 如果题目难理解, 可以适当增加对样例的解释

目录格式: `("[%s](#%s)", 标题, 链接)`

其中标题是展示出来的内容, 应当和题目名称的 h2 标题保持一致.

链接是通过标题转换的, 大概规则是:

- 将空格替换为 `-`
- 删除 `(`, `)`, `?` 等符号
- 全部替换为小写字母

比如 `5 Holding Animals (3pts)` 对应的链接是 `5-holding-animals-3pts`

注意缩进, h2 标题的目录需要两个空格.

## 5 Holding Animals (3pts)

01 背包问题. 多组输入, 每组:

第一行一个整数 N 表示物品个数.

接下来 N 行每行两个整数 W[i], V[i], 分别表示物品 i 的体积和价值.

然后一行一个整数 M 表示背包容量.

问能装到背包里的最大物品价值总和是多少.

N <= 100

W[i], V[i] <= 10,000

M <= 100,000

## 6 Language of Animals (3pts)

问两个点之间的最短路. 只有一组输入.

**[输入格式]**

第一行两个整数 N, M, 分别表示点数和边数.

接下来 M 行每行两个整数 A[i], B[i], 表示这两个点之间有一条无向边 (长为 1).

然后一行一个整数 K, 表示接下来有 K 个询问.

接下来 K 行每行两个整数 X[i], Y[i], 问这两个点之间的最短路径上会经过多少个点.

**[输出格式]**

输出 K 行, 每行一个整数. 如果两个点不连通, 输出 -1

**[数据范围]**

2 <= N <= 200,000

1 <= M <= 300,000

K <= 20

## 7 Feeding Animals I (1pts)

8 个人要喂动物, 每个人喂每种动物要花费一定时间.

问喂饱动物花费的最小时间总和.

注意, 这个题很水, 可以认为: 同一时刻只有一个人在喂动物.

多组输入, 每组:

第一行一个整数 N, 表示动物种数.

接下来 8 行, 每行 N 个整数, 表示一个人喂这 N 种动物分别花费的时间.

对于每组输入, 输出一行, 一个整数.

1 <= N <= 10,000

每个人对于任意一种动物的喂食时间不会超过 10,000

## 8 Feeding Animals II (3pts)

还是喂动物, 一个人可以喂一部分动物, 并且一个人喂动物数量有上限.

问是否所有动物都能被喂.

多组输入, 每组:

第一行两个整数 M, N, 表示人的数量和动物的数量.

接下来 M 行, 每行 N 个整数, `mtx[i][j]` (即 m x n 的矩阵).

`mtx[i][j]` 为 1 表示第 i 个人可以喂第 j 个动物, 为 0 则不可以.

然后一行, 一个整数 K 表示一个人最多可以喂 K 个动物.

对于每组输入, 输出一行, `Yes` 表示所有动物能被喂, `No` 表示不能.

1 <= N, M <= 100

## 10 Alternate Sum (3pts)

计算题.

给定集合 S, 定义 F(S):

- 集合 S 的数字从大到小排序 a[0], a[1], a[2]...
- F(S) = a[0] - a[1] + a[2] - a[3] ...

公式即: $F(S) = \sum_{i=1}^{n}(-1)^{i+1}\times a_i$ (排序后偶数项的和减去奇数项的和)

问 S 的所有的子集的 F(S) 的总和是多少, 答案对 2006 取余.

多组输入, 每组:

第一行一个整数 N, 表示集合大小

接下来 N 行, 每行一个整数

当 N 为 0 时输入停止. (而不是 EOF)

对于每组输入, 输出一行, 一个整数.
