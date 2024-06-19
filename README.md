# Wireshark-Packet-Analysis
Analysis of my first network packet using wireshark: tracing network data
An overview of the key property columns listed for each packet: 
* `No` : The index number of the packet in this packet capture file.
* `Time`: The timestamp of the packet.
* `Source`: The source IP address.
* `Destination`: The destination IP address.
* `Protocol`: The protocol contained in the packet.
* `Length`: The total length of the packet.
* `Info`: Some infomation about the data in the packet (the payload) as interpreted by Wireshark.

![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/9424a15d-6a00-4dd5-97e5-58a98d3dda53)

## Solutions 
1. Identify the source and destination IP addresses involved in this web browsing session.
* On the title bar, type `ip.addr == 142.250.1.139` to filter for traffic associated with a specific IP address. Select the first packet that contains `TCP` on the info field. `addr` means either the source or the destination IP

![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/188041b5-bbbd-4d49-b1a9-c949862a6228)

![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/e4f28e8a-a9b4-4a2a-b05d-84ae369b434d)

* On the title bar, type ip.src == 142.250.1.139 to filter for traffic associated with a specific IP address. src means it is where the packet comes from.

![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/925df8a5-9f53-4120-a02a-1b724fe96dd9)


* On the title bar, type `ip.dst == 142.250.1.139` to filter for traffic associated with a specific IP address. `dst` means it is where the packet goes to.

![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/730bcc2f-7f9d-4db0-b71c-e270d71efbe2)

* On the title bar, type eth.addr == 42:01:ac:15:e0:02 to filter for traffic associated with a specific Ethernet MAC address. addr means either the source or the destination IP.


![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/40e1b234-5e9f-4c88-8c5e-13e33b4a6a39)

2.Examine the protocols that are used when the user makes the connection to the website.

* The TCP destination port of this TCP packet is 80 when ip.addr == 142.250.1.139 which contains the initial web request to an HTPP website that will typically be listening on TCP port 80.

![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/00f7c520-1dda-4538-97d7-f8a8160801af)

* The protocol destination port is TCP when Etherenet address was 42:01:ac:15:e0:02. Source address is 172.21.224.2 and the destination address is 35.235.244.34.
  
![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/9d10fd96-c607-4693-a104-b68e7397086c)

3.Analyze the data packet to identify the type of information sent and received by the systems that connect to each other when the network data is captured.

* On the title bar, type tcp.port == 80 to filter for traffic associated with a specific port number. tcp.port == 80 means only the tcp port is 80 will be shown.

  ![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/31235324-5ad0-4f80-b90b-72e9dfab1834)

* When the filter tcp.port == 80 sets in play, the TTL(time to live) is 64.

* Frame Number: This is essentially the sequence number of a packet within a particular capture. It helps you identify and refer to packets more easily. In your case, a frame number of 37 means it's the 37th packet captured since the beginning of the capture session. This number is assigned sequentially as packets are captured, starting with the number 1 for the first packet.

* Frame Length: This indicates the size of the packet, including all headers and payload, measured in bytes. The frame length of 54 bytes means the total size of the packet is 54 bytes. This size includes everything from the lowest layer (physical layer) up to the highest layer present in the packet that Wireshark can decode. It's useful for understanding the size of the data being transmitted and can help in various analyses, such as identifying potential issues with packet sizes that might indicate fragmentation or other problems.


![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/fb087ff8-2a51-49ab-8b46-780a13c4c2f1)









