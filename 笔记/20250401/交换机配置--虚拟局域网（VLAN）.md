### VLAN（虚拟局域网）

1. 默认所有端口属于VLAN1
2. VLAN ID通常通过端口来划分
3. 只有同一个VLAN编号内的主机才能互相通讯

*****

### 单交换机划分VLAN

+ **假设要将一个普通局域网分割成三个虚拟局域网**

  1. 创建对应的VLAN ID

     ```
     vlan 10
     exit
     vlan 20
     exit
     vlan 30
     exit
     ```

  2. 给VLAN改名字（默认为VLAN0010等）

     ```
     vlan 10
     name XXX
     ```

  3. 选择对应的接口，划入对应的VLAN编号

     + access模式
     + 用来连接网络设备和主机电脑

     ```
     #单接口
     interface fastEthernet 0/1
     switchport access vlan 10
     
     #连续多接口
     interface range f0/2-3
     switchport access vlan 10
     ```

*****************

### 多交换机配置

#### 将连接交换机的端口改成中继模式trunk

```
switchport mode truck
```

******

### 如何查看VLAN信息

```
show vlan
show vlan brief 			//摘要信息
switchport mode trunk 		//查看所有接口信息
```

*******

### 测试

![image-20250401233226888](https://gitee.com/h-jeong/jeongpicgo/raw/master/20250401233226956.png)
