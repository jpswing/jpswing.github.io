---
layout: post
title:  "ACM 的杂七杂八（长期更新）"
date:   2019-02-03
categories: ACM
---

这个 post 用来记录一些做题时学习到的一些技巧之类的东西。

1. 括号序列的性质：（CF 1095E） 
	- 所有前缀中左括号数大于等于右括号数
	- 整个串中左括号数等于右括号数
	-  

2. 次小生成树可以通过改进 kruskal 算法得到（CF 1108F）    

3. 把一个点关于原点对称后，它关于一条通过原点的直线的位置也会改变，i.e. 原来在直线的左侧，之后变为直线的右侧，在直线上则不变（uva 1606）

4. 有多个线段，从左到右维护每个点被哪些线段所覆盖，可以在线段的开始位置与结束后的一个位置标记一下，用红黑树维护，当前位置有某个线段的开始标记则把该线段加入红黑树，有结束标记则删除该线段（CF 1106E）

5. 二分不一定是要 **l + (r - l) / 2**，还可以 **r - (r - l) / 2**，这有些时候可以方便地解决二分陷入死循环的问题（uva 1607）

6. 若 **a = 2^x - 1**，则 **a ⊕ b = a - b (for all 0 <= b <= a)**（CF 1110C）

7. 字典树可以用来做字符串前缀计数：即记录满足某一前缀的字符串有多少个（牛客网某一模拟字节跳动校招题）

8. 如果可以生成极限数据，那么先测试过极限数据再提交！

9. 线性递推关系式可以通过矩阵加速进行求解（如 dp 的转移方程是个线性递推式）（CF 1117D）

10. gcd(x, n)=i 等价于 gcd(x/i, n/i)=1，故可知 gcd(x, n)(x <= n) 中 gcd 为 i 的个数为 phi(n/i)（显然 n/i 要为整数）（uva 11426）

11. 筛法可以用来分解到 N 的所有数的质因数；如果只需求出有哪些质因数，可通过简单修改埃氏筛法实现（CF 1101D 1047C）

12. C++ 的异常处理机制（不知其他语言是否也是如此，暂且就加个定语）是比较慢的，具体可看对于同一问题的这两个提交：1. [用 at 与异常处理来 access map 的元素](https://codeforces.com/contest/1101/submission/50882301)；2. [用常规方法](https://codeforces.com/contest/1101/submission/50882548)

13. 对于没有思路，但是可以模拟的题目，尽量模拟一下，可以用程序模拟

14. 尺取法尽量采用左闭右开的区间。或者说哪里都应该尽量采用左闭右开的区间。

15. 分数比较可以通过约分来实现（CF 1133D）

16. 画图真的很重要！思路很多时候就是模拟的时候出来的。

17. 离散化使用 unique 可以压缩数据（CF 1138C）

18. SCC 缩图可能会产生重边，这没有所谓（CF 1138E）

19. 处理数论问题时将数看成分解后的形式会更利于解题（CF 371B）

20. 平方数的任何倍数在其分解形式中都有至少一个质因数出现两次以上（即指数大于等于2）（CF 588B）

21. 哥德巴赫猜想：任意大于等于 4 的偶数都能分解成两个质数的和（uva 10168）

22. Cayley 定理：一共有 n^(n-2) 种不同的 n 个节点的树（结构或点的标号不同便视为不同的树）（uva 10843）

23. 统计某点被多少个线段覆盖可以用区间查询的 diff 数组解决（因为这本质上就是一个区间加法）。（a[i] = prefix_sum(diff[i])）（CF 296C）

24. 对于边只有 0 和 x 两种权值的图找最短路可以用 0-1 BFS：用 deque，松弛某条边时，若该边是 0，则 push_front，否则 push_back，当最小边权为 0 时可以保证队列里的元素是最短路的在前面，而当最小边权不是 0 时就不一定了。（CF 1064D）

25. floyd 判环（uva 11053）

26. 小于等于 100000 的数中最大因子数为 128，1000000 为 240，1000000000 为 1344（CF 71C）

27. 在图上跑回溯就照节点编号顺序进行回溯就好了！不是在图中跑dfs或bfs！（uva 193）

28. 如果可以通过在一个字符串上任意一个位置添加任意一个字符（一次操作）来获得一个回文，那么同样可以通过在任意一个位置删除一个字符来获得（uva 10739）

29. If the number of dp's state is too much, we may use map to store the values. (uva 11753)

30. In some problems using dp to find a optimal value, if the number of dp's state is too much, we may use memoization search combined with pruning (if possible) to reduce the running time. In order to do this, we may use an additional parameter to keep track of the steps and a global variable to achieve pruning. (uva 11753)

31. A AVL tree which height is **h** has at least F(h) = F(h - 2) + F(h - 1) + 1 nodes(where F(h) means least number of nodes a AVL tree which height is **h** can have). (CF 736A) 

32. do not use **(n - 1) / 2 + 1** to find **ceil(1.0 * n / 2)**, which doesn't work when **(n - 1)** is negative. Use **n / 2 + n % 2** instead.

33. **E(aX + bY) = aE(x) + bE(Y)** (CF 621C)

34. 更相减损法也是 gcd！（CF 347C）

35. bfs 版的 topological sort 里，indegree 为 0 代表这个元素可以放在当前的位置中。

36. Invariant is really important for the correctness of algorithms!!!!!

37. 2D difference array is the difference array of each row's difference array. If we add v to matrix(x1, y1, x2, y2), what we need to do is add(x1, y1, v), add(x1, y2 + 1, -v), add(x2 + 1, y1, -v), add(x2 + 1, y2 + 1, 1). To obtain the original array, just do 2D prefix sum. (HDU 6514)
 
38. Palindrome problems offen require nested-range style dp.

39. 涉及找树上节点的祖先的某些信息的操作可以用倍增法。然而或许也可以用一个栈记住当前 dfs 访问到的节点，然后二分（CF 1059E）

40. dp 构造输出的时候，一般用递归函数根据状态逆推回去即可（uva 757）

41. 阶乘的逆元可以用如下方法计算：**facinv[i] = facinv[i + 1] * (i + 1) % MOD**（初始值用费马小定理算出）

42. Actually breaking code into some modules is more important than you think. 

43. 单纯找最大匹配的网络流用 scaling 似乎会更快（CF 1139E）

44. 匹配可以先只匹配图中的一部分，后面再加边进来再继续匹配，因为只匹配了一部分的图可以看作完整图匹配过程中的中间图（CF 1139E）

45. 可用容斥定理求出区间内与某数互质的数的个数（CF 1139D）

46. The reason why Floyd algorithm works is that in outmost loop, we count something w.r.t. nodes in range [0, k), i.e. each time we are adding a unique node. (iterating from 0 to k) in the outermost loop. (uva 125)

47. 有权树的直径也可以用两次 dfs 求（uva 10308）

48. 路径压缩可以用来优化“链式查询”（CF 534D）

49. 求三点是否在同一直线上可以用叉积：设有三点a, b, c，它们在同一直线上时满足：(b - a) ^ (c - a) == 0（CF 961D）

50. 求一个数学式子的最值时，若式子中有多个变量，看能否把式子变形到同一变量在单独的项中，这样每个项可以单独求最值（leetcode 1131）

51. Doubled area of any triangle with integer coordinates is always integer（可用割补法证明）

52. 枚举子集再枚举子集的补集的子集的复杂度是 O(3^n)

53. 拓扑序唯一的图中最长路径的长度等于顶点数

54. 整数 n 的所有因子中互质的数的对数为 sigma(2 * ki + 1) / 2 + 1，其中 ki 是分解形式中每个质因子上的指数

