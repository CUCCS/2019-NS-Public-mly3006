# 基于 VirtualBox 的网络攻防基础环境搭建

## 实验目的

* 掌握 VirtualBox 虚拟机的安装与使用；
* 掌握 VirtualBox 的虚拟网络类型和按需配置；
* 掌握 VirtualBox 的虚拟硬盘多重加载；

## 实验环境

以下是本次实验需要使用的网络节点说明和主要软件举例：

* VirtualBox 虚拟机
* 攻击者主机（Attacker）：Kali Rolling 2109.2
* 网关（Gateway, GW）：Debian Buster
* 靶机（Victim）： xp-sp3 
## 实验要求

* 虚拟硬盘配置成多重加载
* 搭建虚拟机网络拓扑
* 完成以下网络连通性测试；
    - [x] 靶机可以直接访问攻击者主机
    - [x] 攻击者主机无法直接访问靶机
    - [x] 网关可以直接访问攻击者主机和靶机
    - [x] 靶机的所有对外上下行流量必须经过网关
    - [x] 所有节点均可以访问互联网


##实验步骤
1.**虚拟硬盘配置成多重加载**
>优点 : 省去重新装系统的步骤

2.**网络拓扑**
>由于电脑性能比较差，载不动很多台虚拟机，所以只装了三台，搭建的网络拓扑如图所示:

![](images/tuopu.png)
>为了实现上图的网络环境，三台虚拟机的网络配置如下图所示:

![](images/wi.png)
3.**实验验证**
* 靶机可以直接访问攻击者主机

![](\images\1.png)



* 攻击者主机无法访问靶机
  
![](images/4.png)

* 网关可以直接访问攻击者主机和靶机
  
![](images/5.png)

* 靶机的所有对外上下行流量必须经过网关
  

![](images/6.png)

* 所有节点均可以访问互联网
  
![](images/7.png)


##实验遇到的问题

 **已解决:**
 * [无法解析域名](：https://blog.csdn.net/weixin_40943540/article/details/82943280)
  
* [防火墙配置](https://github.com/CUCCS/2018-NS-Public-jckling/blob/master/ns-0x01/%E5%9F%BA%E4%BA%8EVirtualBox%E7%9A%84%E7%BD%91%E7%BB%9C%E6%94%BB%E9%98%B2%E5%9F%BA%E7%A1%80%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.md)
  具体实现:
  ![](images/9.png)

  ![](images/10.png)

**未解决:**
* xp无法联网，原因是未插入电缆，最后重装了一个一个xp
* debian配置好了网卡，连接的时候无法显示，重装了一个debian
  *由此可见，多重加载是真的方便*
