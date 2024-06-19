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

## Solutions 
1. Identify the source and destination IP addresses involved in this web browsing session.
* On the title bar, type `ip.addr == 142.250.1.139` to filter for traffic associated with a specific IP address. Select the first packet that contains `TCP` on the info field. `addr` means either the source or the destination IP
