# [Free CCNA-Course with NetworkChuck](https://www.youtube.com/watch?v=S7MNX_UD7vY&list=PLIhvC56v63IJVXv0GJcl9vO5Z6znCVb1P&ab_channel=NetworkChuck)

## What is a Network? *Day-0*
- An overview:<br><img src="https://i.ibb.co/GHg8grL/Overview-of-a-Network.png">
- A **switch** simply allows us to connect more than two computers/devices.
- A **router** will help two network talk:<br><img src="https://i.ibb.co/m4S0k0Z/Switches-plus-Router.png">
- **Internet** is simply the combination of routers and switches:<br><img src="https://i.ibb.co/mcTcyHH/Internet.png">
- A **firewall**'s job is to block anything that shouldn't come through or go out and only allow the good stuff:<br><img src="https://i.ibb.co/YdM3g9m/Firewall.png">
- **WAP:** Wireless Access Point:<br><img src="https://i.ibb.co/Y0D79SB/WAP.png">
- Even though we have all these marked stuff (WAP, Switch, Router, Firewall, Modem) in one box, things must be in seperate way in companies thanks to they possess lots of people and lots of valuable data
- ***PS:*** *Network Controllers and Servers will also be covered along with the stuff seen above*

## What is a Switch? *Day-1*
- In order to better understand how smart switches are we need to take a look at its successor: ***Hub***
- Hub send the received package not only to the aimed one but everyone on the network; simply that's why hub sucks and is not smart.<br><img src="https://i.ibb.co/bgws2gt/Hub.png">
- A hub's job is just to repeat the electrical signal as seen above.
- A **ping** message is used to see if the other computer or server is up and can be reached.
    >``` ping 10.1.2.3 ```
- **L2 Address *(Datalink layer)***: MAC Adress
- **L3 Address**: IP Adress
- **Switch** on the other hand transmits the message solely to the desired one.<br><img src="https://i.ibb.co/QbkX67p/Switch.png">
- **CAM (Content Addressable Memory)**: It's the brain of the switch. Actually a table that keeps where (on which port) stands people who are on the network. Switch recognize (know devices) by their **MAC** adresses which is the *Layer 2* address.<br><img src="https://i.ibb.co/0mDt6vb/CAM.png">
- **MAC Address**: It is the unique identifier of each device since been produced. Shouldn't be changed under normal circumstances.
- **L1 *(Layer 1)***: It is the layer that sends the electrical signals. May be called as cables
> Switch is a layer 2 device. It doesn't know anything about more, *IP Adresses (L3) etc.*<br><img src="https://i.ibb.co/M22yxvz/Layer2.png"><br>So when the message is at switch, it's got only L1 and L2!
- But when the message goes to the receiver it's got L3 also:<br><img src="https://i.ibb.co/f8TXpGc/Layer3.png">
- Once a message is sent over the switch, it learns which port the sender and receiver lives at and then stores it at CAM.
> In switch's console: <br> ```enable``` **->** gives root authority <br> ```show mac-adress-table``` **->** shows CAM table<br><img src="https://i.ibb.co/Byqpdg5/Switch-Console-1.png">
- **Frame**: The messages only got L1 & L2 adresses. So all the messages going through switch are frames. *Switch - Frame - Layer 2*
- **Packet**: The messages that got also L3 alongside L1 & L2. So when a message gets to the receiver, it becomes packet.
- However sometimes, network engineers call frames as packets but the actual explainings are like mentioned.
- A **WAP (Wireless Access Point)** behaves like a hub in terms of sending the messages not only to the meant one but to everyone:<br><img src="https://i.ibb.co/x6Np1wP/WAP-is-like-a-Hub.png"><br>This doesn't cause only the info safety being violated but also turning the network traffic into a terrible mess!
- That's why if possible cable connection is prefered.
- *This dumbness of wifi seemed to be fixed with **Wifi-6** (https://www.youtube.com/watch?v=8cmmVEoftEM&ab_channel=NetworkChuck)*