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

* On the title bar, type `ip.dst == 142.250.1.139` to filter for traffic associated with a specific IP address. `dst` means it is where the packet goes to.

![image](https://github.com/YoriTano/Wireshark-Packet-Analysis/assets/106491544/730bcc2f-7f9d-4db0-b71c-e270d71efbe2)


