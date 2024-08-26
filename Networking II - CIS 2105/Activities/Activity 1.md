---
creation date: 2024-08-26T18:14:48
tags:
  - Networking
links:
  - Subnetting
---

# Activity 1

You are given a network ID: `192.168.4.0/24`. And you are required to get **three** subnets with equal number of usable host.

## Answer

Instead of three subnets we will be using **four**. Therefore the host will be $65$ and with a subnet mask of $/26$.

|  Network ID   | Subnet Mask |         Host ID Range         | Usable host | Broadcast ID  |
|:-------------:|:-----------:|:-----------------------------:|:-----------:|:-------------:|
|  192.168.4.0  |     /26     |  192.168.4.1 - 192.168.4.62   |     62      | 192.168.4.63  |
| 192.168.4.64  |     /26     | 192.168.4.65 - 192.168.4.126  |     62      | 192.168.4.127 |
| 192.168.4.128 |     /26     | 192.168.4.129 - 192.168.4.190 |     62      | 192.168.4.191 |
| 192.168.4.192 |     /26     | 192.168.4.193 - 192.168.4.254 |     62      | 192.168.4.255 |
