# 线性表

## 一、线性表的定义和基本操作

### 1. 线性表的定义

线性表是具有相同数据类型的n\(n&gt;=0\)个数据元素的有限序列。其中n为表长，当n=0时该线性表是一个空表。若用L命名线性表，其一般表示如下：

$$
L = (a1, a2,  ……, an)
$$

### 2. 线性表的基本操作

基础操作的实现取决于采用哪一种存储结构，存储结构不同，算法的实现也不同。

* InitList\(&L\)
* Length\(L\)
* LocateElem\(L, e\)
* GetElem\(L, i\)
* ListInsert\(&L, i, e\)
* ListDelete\(&L, i, &e\)
* PrintList\(L\)
* Empty\(L\)
* DestroyList\(&L\)

## 二、线性表的顺序实现

### 1. 顺序表的定义

用一组地址连续的存储单元，一次存储线性表中的数据元素，从而使逻辑相邻的两个元素在物理位置上也相邻。一维数组可以是静态分配的，也可以是动态分配的。

```text
//静态分配
#define MaxSize 50                //定义线性表最大容量
typedef struct{
    ElemType data[Maxsize];       //顺序表的元素
    int length;                   //顺序表的当前长度
}SqList;

//动态分配
#define InitSize 100              //表长度的初始定义
typedef struct{
    ElemType *data;               //动态分配数组的指针
    int MaxSize, length;          //数组的最大容量和当前长度
}SqList;
```

顺序表最主要的特点是随机访问，即通过首地址和元素序号可以在O\(1\)的时间找到制定的元素，但是插入和删除操作需要移动大量元素。

### 2. 顺序表上基本操作实现

