# Upload File
1. Client --request--> Namenode;
2. Namenode --return list of available Datanode--> Client;
3. Client split the file into pieces;
4. Client upload to DataNode, AND do backup(replication);
5. DataNode confirm reception to client and update to Namenode;

# NameNode
1. Manage DataNode;
2. Monitor the heartbeat of DataNode;
3. Recover the file;

## When NameNode Starts
Load and read the FS image:
(1)从 fsimage 中读取该 HDFS 中保存的每一个目录和每一个文件
(2)初始化每个目录和文件的元数据信息
(3)根据目录和文件的路径，构造出整个 namespace 在内存中的镜像
(4)如果是文件，则读取出该文件包含的所有 blockid，并插入到 BlocksMap 中
(5) 整个 HDFS 的目录结构在内存中就已经初始化完毕，所缺的就是每 个文件对应的 block 对应的 datanode 列表信息。这些信息需要从 datanode 的 blockReport 中 获取，所以加载 fsimage 完毕后，namenode 进程进入 rpc 等待状态，等待所有的 datanodes 发送 blockReports。

# HA (high availability)
Active and Standby NN share states with JournalNode

[reference1](https://zhuanlan.zhihu.com/p/374651310)
[r20](https://www.geeksforgeeks.org/hadoop-yarn-architecture/)

# YARN

## General Process
Client submits an application
The Resource Manager allocates a container to start the Application Manager
The Application Manager registers itself with the Resource Manager
The Application Manager negotiates containers from the Resource Manager
The Application Manager notifies the Node Manager to launch containers
Application code is executed in the container
Client contacts Resource Manager/Application Manager to monitor application’s status
Once the processing is complete, the Application Manager un-registers with the Resource Manager

## Application Master VS. Application Manager:
Manager reject or accepts jobs submitted to Resource Managers, keep a list of submitted jobs;
Master is responsible for the execution a signle job assigned to Node by Resource Manager;
