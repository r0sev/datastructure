
### 整体思路：
  1. 先统计每个字符的出现字数（频度），并创建一个频度数组，用于存放每个字符出现的次数，共256个ascii
  2. 根据频度数组probability 创建优先级队列，出现0次的就不入队了，其余的按递增顺序在队(ps:不如说链表了..)中排列
  3. 从队头开始取元素，每取两个创建合并为一个新的哈夫曼树节点，并打包好(封装合并了priority)后重新入队，直到队中只剩1个结点
  4. 创建哈夫曼树的根节点并指向(pQueue)queue中的'最后一个元素' 表现为：queue->first，因为每次插入删除都会操作first指针
  5. 根据已创建的Huffman树建立对应的Huffman表(Table)
  6. 根据表加密字符串
  7. 根据树解密相应字符串
