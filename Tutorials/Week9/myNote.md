中序遍历binary search tree得到递增序列



### 二叉排序树的查找

![Screenshot 2024-07-08 at 12.06.13 pm](/Users/siruichen/Desktop/9024/COMP9024/Tutorials/Week9/Screenshot 2024-07-08 at 12.06.13 pm.png)

递归查找

![Screenshot 2024-07-08 at 12.08.48 pm](/Users/siruichen/Desktop/9024/COMP9024/Tutorials/Week9/Screenshot 2024-07-08 at 12.08.48 pm.png)



### 二叉排序树的插入

![Screenshot 2024-07-08 at 12.12.24 pm](/Users/siruichen/Desktop/9024/COMP9024/Tutorials/Week9/Screenshot 2024-07-08 at 12.12.24 pm.png)

不允许两个节点相等

每个新插入的节点都是叶子结点



### 二叉排序树的删除（重点）

**先搜索找到目标结点**

#### case1：被找到的节点是叶子结点

op: 直接删除即可

#### case2：结点只有左子树或只有右子树

op：让z的子树称为z父结点的子树（让z的子树代替z的位置）

#### case3：结点既有左子树又有右子树

直接前驱和直接后继

**结点的后继：遍历其右子树时访问的第一个结点，即右子树中最左下的结点；**

**结点的前驱：若没有左孩子其左标志为 1 ，则左链为线索，指向其前驱 ；否则，遍历左子树时最后一个访问的结点（左子树中最右下的结点）位其前驱。（左子树右下）**



Op: 则令z的直接后继（或直接前驱）替代z，然后从二叉排序树中删去这个直接后继（或直接前驱），这样就转换成了第一或第二种情况。 因为直接后继没有左子树，直接前驱没有右子树。

代码实现中，BiTreeDelete中，case 11的情况，先换成successor，造成inconsistency，然后recursively调用自己

BTW，找successor，先右走一步，在一直左走

**Pointer to pointer 应该会考**