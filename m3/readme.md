
# TASK3.1-3.4
## Workflow:


<details>
<summary> Task3.1  </summary>
<br>
Created three networkss according to instructions. Configured static IP addresses in Enterprise Net with network 10.2.30.0/24 and checked connection.


![Screen1](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.1/screenshots/Screenshot_1.png)


Configured Data Center network with static IP addresses by rule 1.30.2.0/24 and checked connection.


![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.1/screenshots/Screenshot_2.png)


Switched Ethernet adapter to Wi-Fi module on Client 3 PC and configured wireless connection in Home Office network and checked connection. 


![Screen3](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.1/screenshots/Screenshot_3.png)


Link to Packet Tracer project file: [task3.1.pkt][task3.1-pkt]
#### Additional task

Installed Wireshrk, captured trafic and selected an TCP-segment from captured part. Found and highlighted channel, network and transport layer header. Highlighted source and destination MAC, IP addresses and port numbers.


![Screen4](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.1/screenshots/Screenshot_4.png)
</details>

<details>
<summary>Task3.2</summary>
<br>
Connected task3.1 networks by Internet based on three routers connected according to task. Divided network 40.1.2.0/24 to 4 networks and assign the desire addresses to the corresponding ports:

 -  40.1.2.0/26
 - 40.1.2.64/26
 - 40.1.2.128/26
 - 40.1.2.192/26
 
 Assigned GE0/0 interface of routers with route:
 
 - ISP1 - 10.2.30.1/24
 - ISP2 - 40.1.2.192/26
 - ISP3 - 1.30.2.1/24

Configured default gateways on end devices and checked connection in networks from end device to network router.
 ![Screen5](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/screenshots/Screenshot_6.png)
 ![Screen6](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/screenshots/Screenshot_6.png)
 ![Screen7](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/screenshots/Screenshot_7.png)


##### Data Center VLAN Configuration

- Changed subnet mask on servers from 255.255.255.0 to 255.255.255.192 and cheked connection.


![Screen9](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/screenshots/Screenshot_9.png)


- Created VLANs on Data Center Switcha and assigned them to corresponding ports, checked connection once again


![Screen10](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/screenshots/Screenshot_10.png)


##### Additional task - VLAN routing

- Switched FE0/1 port mode from Access to Trunk
- Configured routing on ISP3 router through CLI:


```
interface GigabitEthernet0/0.2
encapsulation dot1Q 2
ip address 1.30.2.1 255.255.255.192
interface GigabitEthernet0/0.3
encapsulation dot1Q 3
ip address 1.30.2.65 255.255.255.192
interface GigabitEthernet0/0.4
encapsulation dot1Q 4
ip address 1.30.2.129 255.255.255.192
```

- Checked connection between servers again


![Screen11](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/screenshots/Screenshot_11.png)


Link to Packet Tracer project file: [task3.2.pkt][task3.2-pkt]
</details>

<details>
<summary>Task3.3</summary>
<br>

Configured static routing on routers according to subnets obtained from previous tasks and checked connections.

| Router | Interface | Network IP-address | Host IP-address |
| ---- |--------| ---------------- | ------------ |
| ISP1 | GE0/0 | 10.2.30.0/24 | 10.2.30.1 |
| | GE1/0 | 40.1.2.0/26 | 40.1.2.1 |
| | GE2/0 | 40.1.2.64/26 | 40.1.2.65|
| ISP2 | GE0/0 | 40.1.2.192/26 | 40.1.2.193 |
| | GE1/0 | 40.1.2.0/26 | 40.1.2.2 |
| | GE3/0 | 40.1.2.128/26 | 40.1.2.129 |
| ISP3 | GE0/0.2 | 1.30.2.0/26 | 1.30.2.1 |
| | GE0/0.3 | 1.30.2.64/26 | 1.30.2.65 |
| | GE0/0.4 | 1.30.2.128/26 | 1.30.2.129 |
| | GE2/0 | 40.1.2.64/26 | 40.1.2.66 |
| | GE3/0 | 40.1.2.128/26 | 40.1.2.130 |
| Home | Internet | 40.1.2.192/26 | 40.1.2.194 |

 
 ![Screen12](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.3/screenshots/Screenshot_12.png)


![Screen13](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.3/screenshots/Screenshot_13.png)


Erased static routing from Internet routers and configured RIP-protocol routing and checked connection once again.


![Screen14](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.3/screenshots/Screenshot_14.png)


![Screen15](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.3/screenshots/Screenshot_15.png)


Link to Packet Tracer project file: [task3.3.pkt][task3.3-pkt]
</details>

<details>
<summary>Task3.4</summary>
<br>

Configured Enterprise DHCP Server by creating DHCP pool and default gateway (ISP1 GE0/0 interface). Switched Clien1 and Client2 IP Configuration mod to DHCP. Made same steps for Home network and Home Router.

 ![Screen16](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.4/screenshots/Screenshot_16.png)


![Screen17](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.4/screenshots/Screenshot_17.png)


Configured DNS service on DNS Server adding domains wrldwde1.com and wrldwdeblog.com to DNS table. Configured DNS server address on DHCP servers and update configs on Clients PCs. Ping domains from Client PCs.


![Screen18](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.4/screenshots/Screenshot_18.png)


Added a Home Server, configured IP-address and edit an .html file of home page. Configured Port Forwarding on Home Router and added Home Server domain *wrldwdehome.com* to DNS Server table. Checked home page from Client1 PC.


![Screen19](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.4/screenshots/Screenshot_19.png)


Link to Packet Tracer project file: [task3.4.pkt][task3.4-pkt]
</details>


[//]: #
[git-repo-url]: <https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4>
[task3.1-pkt]:<https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.1/DevOps_Autumn2021_task3.1.pkt>
[task3.2-pkt]:<https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/DevOps_task3.2.pkt>
[task3.3-pkt]:<https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/DevOps_task3.3.pkt>
[task3.4-pkt]:<https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m3/task3.2/DevOps_task3.4.pkt>