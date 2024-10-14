# Packet-Analysis-with-Wireshark

## Overview
Using Wireshark to examine a sample packet capture file and filter the network traffic data.

### Open Packet Capture File.
Double-click the sample .pcap file on the desktop (outlined in red). This will open the file within Wireshark.
![image](https://github.com/user-attachments/assets/3b555282-3fab-4764-b443-5ee73d559fdc)

### Apply a basic Wireshark filter and inspect a packet.
Open a packet in Wireshark for more detailed exploration and filter the data to inspect the network layers and protocols contained in the packet.

Enter the following filter for traffic associated with a specific IP address: "ip.addr == 142.250.1.139". Enter this into the Apply a display filter text box immediately above the list of packets (outlined in red). And press enter.
![Screenshot 2024-10-14 120448](https://github.com/user-attachments/assets/c4e2f34f-4b07-4930-9f08-00d3ec21797b)

The list of packets displayed is now significantly reduced and contains only packets where either the source or the destination IP address matches the address entered. Now only two packet colors are used: light pink for ICMP protocol packets and light green for TCP (and HTTP, which is a subset of TCP) packets.

Double-cicking on a packet will open up a packet details pane window.
![Screenshot 2024-10-14 121325](https://github.com/user-attachments/assets/a2aa6dca-c6d5-46aa-838a-6ef3d87c92c5)

The upper section of this window contains subtrees where Wireshark will provide an analysis of the various parts of the network packet. The lower section of the window contains the raw packet data displayed in hexadecimal and ASCII text. There is also placeholder text for fields where the character data does not apply, as indicated by the dot (“.”).
Double-clicking on the first subtree that begins with "Frame" provides you with details about the overall network packet, or frame, including the frame length and the arrival time of the packet. At this level, you’re viewing information about the entire packet of data.
The next subtree "Ethernet II" contains details about the packet at the Ethernet level, including the source and destination MAC addresses and the type of internal protocol that the Ethernet packet contains.
The subtree "Internet Protocol Version 4" provides packet data about the Internet Protocol (IP) data contained in the Ethernet packet. It contains information such as the source and destination IP addresses and the Internal Protocol (for example, TCP or UDP), which is carried inside the IP packet.
The final subtree listed "Transmission Control Protocol" provides detailed information about the TCP packet, including the source and destination TCP ports, the TCP sequence numbers, and the TCP flags.

The filter is useful for tasks such as filtering packets based on source ip addresses (ip.src == x), destination ip addresses (ip.dst == x), physical MAC addresses (eth.addr == x), IP addresses, specific port traffic (udp.port == x), and specific text data within a packet (tcp contains "x").
