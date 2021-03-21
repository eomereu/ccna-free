# [Free CCNA-Course with NetworkChuck](https://www.youtube.com/watch?v=S7MNX_UD7vY&list=PLIhvC56v63IJVXv0GJcl9vO5Z6znCVb1P&ab_channel=NetworkChuck)

## What is a Network? *EP-0*
- An overview:<br><img src="https://i.ibb.co/GHg8grL/Overview-of-a-Network.png">
- A **switch** simply allows us to connect more than two computers/devices.
- A **router** will help two network talk:<br><img src="https://i.ibb.co/m4S0k0Z/Switches-plus-Router.png">
- **Internet** is simply the combination of routers and switches:<br><img src="https://i.ibb.co/mcTcyHH/Internet.png">
- A **firewall**'s job is to block anything that shouldn't come through or go out and only allow the good stuff:<br><img src="https://i.ibb.co/YdM3g9m/Firewall.png">
- **WAP:** Wireless Access Point:<br><img src="https://i.ibb.co/Y0D79SB/WAP.png">
- Even though we have all these marked stuff (WAP, Switch, Router, Firewall, Modem) in one box, things must be in seperate way in companies thanks to they possess lots of people and lots of valuable data
- ***PS:*** *Network Controllers and Servers will also be covered along with the stuff seen above*

## What is a Switch? *EP-1*
- In order to better understand how smart switches are we need to take a look at its successor: ***Hub***
- Hub send the received package not only to the aimed one but everyone on the network; simply that's why hub sucks and is not smart.<br><img src="https://i.ibb.co/bgws2gt/Hub.png">
- A hub's job is just to repeat the electrical signal as seen above.
- A **ping** message is used to see if the other computer or server is up and can be reached.
    >``` ping 10.1.2.3 ```
- **L2 Address *(Datalink layer)***: MAC (Media Access Control) Adress
- **L3 Address**: IP Adress
- **Switch** on the other hand transmits the message solely to the desired one.<br><img src="https://i.ibb.co/QbkX67p/Switch.png">
- **CAM (Content Addressable Memory)**: It's the brain of the switch. Actually a table that keeps where (on which port) stands people who are on the network. Switch recognize (know devices) by their **MAC** adresses which is the *Layer 2* address.<br><img src="https://i.ibb.co/0mDt6vb/CAM.png">
- **MAC Address**: It is the unique identifier of each device since been produced. Shouldn't be changed under normal circumstances.
- **L1 *(Layer 1)***: It is the layer that sends the electrical signals. May be called as cables
> Switch is a layer 2 device. It doesn't know anything about more, *IP Adresses (L3) etc.*<br><img src="https://i.ibb.co/M22yxvz/Layer2.png"><br>So when the message is at switch, it's got only L1 and L2!
- But when the message goes to the receiver it's got L3 also:<br><img src="https://i.ibb.co/f8TXpGc/Layer3.png">
- Once a message is sent over the switch, it learns which port the sender and receiver lives at and then stores it at CAM.
> In switch's console: <br> ```enable``` **->** gives root authority <br> ```show mac-adress-table``` **->** shows CAM table<br><img src="https://i.ibb.co/Byqpdg5/Switch-Console-1.png">
- **Frame**: The messages only got L1 & L2 adresses. So all the messages going through switch are frames. 
- *Switch - Frame - Layer 2*
- **Packet**: The messages that got also L3 alongside L1 & L2. So when a message gets to the receiver, it becomes packet.
- However sometimes, network engineers call frames as packets but the actual explainings are like mentioned.
- A **WAP (Wireless Access Point)** behaves like a hub in terms of sending the messages not only to the meant one but to everyone:<br><img src="https://i.ibb.co/x6Np1wP/WAP-is-like-a-Hub.png"><br>This doesn't cause only the info safety being violated but also turning the network traffic into a terrible mess!
- That's why if possible cable connection is prefered.
- *This dumbness of wifi seemed to be fixed with **Wifi-6** (https://www.youtube.com/watch?v=8cmmVEoftEM&ab_channel=NetworkChuck)*
- How switch finds the target:<br><img src="https://i.ibb.co/vJRs7J6/ARP.png">
- **ARP**: *Address Resolution Protocol* This frame is critical to find out which MAC address is related to the IP address of the destination<br>
- **Broadcast Address**: The unknown phase of the receiver's MAC address. When a switch sends something to this address it will simply go to everyone:<br><img src="https://i.ibb.co/fQwFL3x/ARP-Broadcasting.png">
- **ICMP**: *Internet Control Message Protocol*

## What is a Router? *EP-2*
- A router's job is to connect networks
- When we talk about a network, we refer to a group of IP addresses:<br><img src="https://i.ibb.co/6ZhNZML/Networks.png">
- When we try to ping someone who is not on the same network with us *(within the same IP range)* it will simply set the destination IP as the **Gateway Address** which is also known as **Router IP Address**. Because it knows that, the destination is not on the same network *(within the range)* so it's gonna try to reach the router to get some help:<br><img src="https://i.ibb.co/TTZnyvL/Ping-Different.png"><br><img src="https://i.ibb.co/NFyZ28w/Dest-IP.png"><br><img src="https://i.ibb.co/6sbXQLL/Gateway-Router.png">
- At this point we need someone to get help to reach the other network and here is where *router* comes in.
- *Router - Packet - Layer 3*
- Once the message received router, it's got a small problem in the first place. It's not known where to send him. Layer 2 info is missing:<br><img src="https://i.ibb.co/4KHdDLf/L2-Missing.png">
- At this point, router sends out an ARP message to find out where the destination is:<br><img src="https://i.ibb.co/TPYv8By/Router-ARP-Broadcast.png">
- In the end when we check the message when it's at the source yet, we see that in Layer 3 it's from source to destination (in another network) but in Layer 2 it's from source to its router:<br><img src="https://i.ibb.co/djNFR4z/In-the-end.png"><br>So here Layer 3 has the directions for router; Layer 2 has the directions for the switch.
- So at the higher level, the message at the router is like:<br><img src="https://i.ibb.co/wM1BKxc/At-the-higher-level.png">

> In router's console/CLI: <br> ```enable``` **->** gives root authority <br> ```show ip route``` **->** shows CAM table<br><img src="https://i.ibb.co/KzCr3bV/Simple-Route-Map.png"> <br>```show bgp ipv4 unicast``` **->** shows the route map of a bigger router

### DNS *Sneak Peak*
- In practical world, things are not going over IP adresses but domain names, like google.com etc.
- At this point a **DNS (Domain Name Server)** comes in and gives us the matching IP of that sepcific domain name: <br><img src="https://i.ibb.co/dbgyPww/DNS-Answer.png">