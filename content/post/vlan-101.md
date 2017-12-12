+++
title = "VLAN 101"
date = 2017-10-15T21:15:56+05:45
draft = false
summary = """
Introduction to VLAN
"""
tags = ["networking"]
math = false
+++


XYZ is a small business office. It needs 20 different hosts to be connected. Ten for IT department, five for finance and, remaining five for sales. Due to security purpose, finance data should not be seen by the sales or, the IT department and, vice versa.

If you are asked to setup the network, how would you do this? The infeasible answer is self evident: Use three different switches in each department. However, if you do this, the cost will increase and many port will be left unused. 

The best solution is creating virtual local area network in, a single, 24-port switch. The host of IT department, sales and, finance are connected to the same switch and, three logical portion are made as follows:

|VLAN|Hosts|Departments|Swithport|
|---|---|---|---|
|10|Computer C1-10|IT|Port 1 to 10|
|20|Computer C11-15|Sales|Port 11 to 15|
|30|Computer C16-20|Fainance|Port 16 to 20|

In this way, logical partition is created in switch (layer 2), which is called VLAN. We can name the VLAN. In our case, Computer C1-C10 of IT department is assigned VLAN 10,  C11-C15 of sales is assigned VLAN 20 and, C16-C20 is assigned VLAN 30.

In cisco switch, VLAN can be numbered from 2 to 4049. VLAN 1, which is cisco default, can be used but not modified or, deleted. Within the range 2-1005, you can create use, modify and, delete VLAN. 1005-4049 is extended VLAN which has an always active state.
 
![](../../img/vlan-in-cisco-switch.png)

Now assume computer 17 sends broadcast packet. Will this packet be forwarded to sales or, IT department? – NEITHER, because VLAN is a broadcast domain of its own. Computers from IT or, finance will not get the packet. VLAN helps control the reach of broadcast frame. Also, Unicast and multicast frames are forwarded within VLAN only.

{{%alert "info"%}} Next -> configuring VLAN in cisco switch(stay tuned){{%/alert%}}

author: [Pratik Gautam](https://github.com/Pratik855)
