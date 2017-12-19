# 数据结构与算法 :dizzy:
## 线性表
顺序表是一种典型的线性结构，是最简单、最常用的数据结构。
在计算机中线性表可以采用两种方式来保存，一种是顺序存储结构，另一种是链式存储结构.
- [顺序表结构](./src/dataStructure/orderList)
- [链表结构](./src/dataStructure/linkedList)

## 栈结构
栈结构是一种线性结构，栈结构包括两类：
- [顺序栈结构](./src/dataStructure/stack)：即使用一组地址连续的内存单元依次保存栈中的数据。在程序中，可以定义一个指定大小的结构数组来作为栈，序号为0的元素就是栈底，再定义一个变量top保存栈顶的序号即可。
- 链式栈结构：即使用链表形式保存栈中各元素的值。链表首部（head引用所指向元素）为栈顶，链表尾部（指向地址为null）为栈底。

栈结构是按照“后进先出”的原则处理节点数据的。在栈结构中，只有栈顶元素是可以访问的。一般栈结构的基本操作有两个：
- 入栈（Push）：将数据保存到栈顶的操作。进行入栈操作前，先修改栈顶引用，使其向上移一个元素，然后将数据保存到栈顶引用所指的位置。
- 出栈（Pop）：将栈顶的数据弹出的操作。先取出栈顶指针所指位置的数据，再通过 修改栈顶引用，使其指向栈中的下一个元素。

## 队列结构
从数据的逻辑结构来看，队列（Queue）是一种线性结构。如果从数据的存储结构来进一步划分，队列结构包括两类。
- [顺序队列结构](./src/dataStructure/queue)：即使用一组地址连续的内存单元依次保存队列中的数据。在程序中，可以定义一个指定大小的结构数组作为队列。
- 链式队列结构：即使用链表形式保存队列中各元素的值。

从数据的运算角度来分析，队列结构是按照“先进先出”的原则处理结点数据的。在队列结构中，数据运算非常简单。一般队列结构的基本操作只有
- 入队列：将一个元素添加到队尾（相当于到队列最后排队等候）
- 出队列：将队头的元素取出，同时删除该元素，使后一个元素成为队头。

## 树结构
树（Tree）结构是一种描述非线性层次关系的数据结构，其中重要的是树的概念。树是n个数据结点的集合，在该集合中包含一个根结点，根结点之下分布着一些互不交叉的子集合，这些子集合是根结点的子树。树结构的基本特征如下：
- 在一个树结构中，有且仅有一个结点没有直接前驱，这个结点就是树的根结点；
- 除根结点外，其余每个结点有且仅有一个直接前驱；
- 每个结点可以有任意多个直接后继。
从树的定义可以看出，树具有层次结构的性质。而从数学的角度来看，树具有递归的特性。在树中的每个结点及其后的所有结点构成一个子树，这个子树也包括根结点。

在树结构中，二叉树是最简单的一种形式。在研究树结构时，二叉树是树结构内容中的重点。二叉树的描述相对简单，处理也相对简单，而且更为重要的是任意的树都可以转换成对应的二叉树。
### 二叉树
二叉树是树结构的一种特殊形式，它是n个结点的集合，每个结点最多只能有两个子结点。二叉树的子树仍然是二叉树。二叉树的一个结点上对应的两个子树分别称为左子树和右子树。由于树有左右之分，因此二叉树是有序树。

二叉树可以进一步细分为两种特殊的类型，满二叉树和完全二叉树：
- 满二叉树：在二叉树中除最下一层的叶结点外，每层的结点都有两个子结点，即这是一个每一层都不缺结点的完整二叉树。
- 完全二叉树：在二叉树中除二叉树最后一层外，其他各层的结点数都达到最大个数，且最后一层叶结点按照从左到右的顺序连续存在，只缺最后一层右侧若干结点。

从上述二叉树和完全二叉树的定义可以看出，满二叉树一定是完全二叉树，而完全二叉树不一定是满二叉树，因为其没有达到完全满分支结构。

按照数据的存储方式，树结构可以分为顺序存储结构和链式存储结构两种：
- 二叉树的顺序存储：与线性表类似，树结构的顺序存储一般采用一位结构数组来表示。这里的关键是定义合适的次序来存放树中各个层次的数据。如果采用顺序存储方式，可以将其按层来存储，即先存储根结点，然后从左至右依次存储下一层结点的数据....,直到所有的结点数据完全存储。
二叉树的链式存储结构定义代码实例：
```java
static final int MAXLEN = 100;		// 最大结点数
char[] SeqBinaryTree = new char[MAXLEN];	// 定义保存二叉树数组
```
- [二叉树的链式存储](./src/dataStructure/tree)：与线性结构的链式存储类似，二叉树的链式存储结构包含结点元素及分别指向左子树和右子树的引用。
二叉树的链式存储结构定义代码实例：
```java
class CBTType{					// 树结点的类型结构
	String data;				// 结点保存的数据
	CBTType left;				// 指向的左子树
	CBTType right;				// 指向的右子树
}
CBTType root = null;			// 定义二叉树根结点引用
```

## 图结构
### 无向完全图
对于一个包含N个顶点的无向完全图，其总的边数为 N(N-1)/2
### 有向完全图
对于一个包含N个顶点的有向完全图，其边的总数为 N(N-1)，无向完全图的两倍。
### 连通、连通图和连通分量
1. 如果图结构中两个顶点之间有路径，则称这两个顶点是连通的。这里需要注意连通的两个顶点可以不是邻接顶点，只要有路径连接即可，可以途径多个顶点。
2. 如果无向图中任意两个顶点都是连通的，那么这个图便称为连通图。如果无向图中包含两个顶点不是连通的，那么这个图便称为非连通图。
3. 无向图的极大连通子图称为该图的连通分量。

对于一个连通图，其连通分量有且只有一个，那就是该连通图自身。
### 强连通图和强连通分量
1. 如果两个顶点之间有路径，也称为这两个顶点是连通的。需要注意的是，有向图中边是有方向的。
2. 如果有向图中任意两个顶点都是连通的，则称该图为强连通图。如果有向图中包含两个顶点不是连通的，则称该图为非强连通图。
3. 有向图的极大强连通子图称为该图的强连通分量。

# 数据结构与算法 面试题(Java版) :sparkles:

- [单例模式的六种实现](./src/review02)
- [二位数组中的查找](./src/review03)
- [字符串替换空格](./src/review04)
