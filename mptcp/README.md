# MPTCP 仿真实验

标签（空格分隔）： MPTCP SDN

---

##说明
使用Mininet进行MPTCP仿真实验。

##重要文件/目录列表
1. single_switch_2_hosts.py:
单交换机，2主机。

```
+--------------------------------+
|                                |
|       OVS                      |
+-+-+-------------------+--+-----+
  | |                   |  |
  | |                   |  |
  | |                   |  |
  | |                   |  |
  | |                   |  |
  | |                   |  |
 ++-+--+              +-+--+--+
 |     |              |       |
 |     |              |       |
 | H1  |              | H2    |
 |     |              |       |
 +-----+              +-------+

```
2.dua_switch_2_hosts_ndiffports.py
```
+-----------------------+       +-------------------------+
|                       +-------+                         |
|       s1              +-------+        s2               |
+------+--+-------------+       +---------+--+------------+
       |  |                               |  |
       |  |                               |  |
     +-+--+-+                           +-+--+-+
     |      |                           |      |
     |      |                           |      |
     |  h1  |                           | h2   |
     |      |                           |      |
     +------+                           +------+

```

3. fattree_k4.py

该脚本构建k=4的胖叔网络,并在网络启动之后执行网络测试:

- 随机挑选N对主机(N为主机数目),每个主机既作为Server也作为client;
- 每隔五秒选取一堆主机进行tcp通信,持续60s
- 分析服务端生成的报告
