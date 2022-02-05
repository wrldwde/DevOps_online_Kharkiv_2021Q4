

# TASK6.1
## Workflow:

#### 1) To build this scheme of network we need VM1 (works like gateway for VM2) with two interfaces (NAT and internal) and VM2 with internal interface. Also we need to configure port forwarding on VM1 NAT interface to provide connection to VM2:

![Screen1](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_1.png)

![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_2.png)

![Screen3](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_3.png)

#### 2) To complete this point we need to perform next steps:
##### 1. Configure internal interface (enp0s8) on VM1:
```
sudo ip addr add 192.168.1.1/24 broadcast 192.168.1.255 dev enp0s8
sudo ip link set enp0s8 up
```

##### 2. Configure internal interface (enp0s3) on VM2:
```
sudo ip addr add 192.168.1.10/24 broadcast 192.168.1.255 dev enp0s3
sudo ip link set enp0s3 up
sudo ip route add default via 192.168.1.1 dev enp0s3
sudo echo nameserver 8.8.8.8 >> /etc/resolv.conf
sudo echo nameserver 4.4.4.4 >> /etc/resolv.conf
```

##### 3.Enable IP forwarding on VM1:
``
sudo echo 1 > /proc/sys/net/ipv4/ip_forward
``

##### 4. Add `iptables` rules on VM1 to forward SSH traffic to VM2 and to masquerade traffic from VM2:
```
sudo iptables -t nat -A POSTROUTING -o enp0s3 -j MASQUERADE
sudo iptables -t nat -A PREROUTING -i enp0s3 -p tcp --dport 2223 -j DNAT --to-destination 192.168.1.10:22
```

#### 3) Route from VM2 to host:
``
traceroute 8.8.8.8
``

![Screen4](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_4.png)

#### 4) Access to internet from VM2:
``
ping 8.8.8.8
``

![Screen5](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_5.png)

#### 5) To determine resourse by IP address, command `whois` was used:
``
whois 8.8.8.8
``

![Screen6](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_6.png)

#### 6) Command `dig` was used to determine *emap.com* resource IP address:
``
dig epam.com
``

![Screen7](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_7.png)

##### 7) To determine routes and routing table at all, command `route print` was used
``
route print
``

![Screen8](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_8.png)

#### 8) Traceroute to *google.com*:

![Screen9](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m6/task6.1/Screens/S_9.png)






[//]: #
[git-repo-url]: <https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4>