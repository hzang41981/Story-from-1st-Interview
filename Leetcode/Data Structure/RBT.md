# AVL
左旋 => 逆时针；

插入之后检查是否失衡；
失衡之后，插入节点的最近的失衡祖先（最小失衡指数）
四种失衡状态：
LL => 右旋
left tree of left node失衡，right tree of left node become left tree of new right node（after rotation）；
RR => 左旋
left tree of right node become new right tree of the new left node;
LR => 左旋，右旋
先左旋转换成LL，然后处理LL；
RL => 右旋，左旋

# RBT
RBT比AVL平衡性差点；
less rotation when insert, but poorer search performance than AVL;
## 定义
1. Root Property: root must be black;
2. red property: children of red are black (no neighbout of red is red, but neighbour of black can be black);
3. black property: simple path from node the leaf node have same number of black nodes (null is considered as leaf node);
4. Height of RBT = 2*log(n+1);

## Black Height
Number of black nodes on any simple path from a node to a leaf;

## Insertion
1. if empty => insert newNode as root;
2. if not empty => insert as leaf node of color red;
3. if parent is red => check color of parent's sibling of newNode; (if parent is black ???)
4.1 if sibling is red, then recolor and check parent's parent of newNode (if not root recolor); 
5.1 Repeat step 4.1;
4.2 if sibling is black or NUll, then rotation and recolor;
