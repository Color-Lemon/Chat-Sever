# ChatServer
基于muduo库的集群聊天系统（C++实现）
 编译方式
 1.首先将build目录下的文件删除
 cd build
 rm -rf *
 2.编译
 cmake ..
 make
 
 开发环境以及用到的技术：
◆	在Windows的VSCode远程连接ubuntu的开发环境下，通过CMake构建集成编译环境
◆	采用C/S架构，基于MVC设计模式降低了网络模块和业务模块的耦合度
◆	模仿muduo网络库的one loop per thread设计思路与它的对外接口，实现服务器编程
◆	通过Json的数据交换格式进行信息通信，后台数据使用 MySQL 进行存储及相应操作
◆	使用unordered_map容器存储消息类型和对应消息的方法，再根据该方法执行相应的操作
◆	通过配置nginx的tcp负载均衡实现服务器集群，使用发布-订阅的Redis消息队列实现跨服务器通信
