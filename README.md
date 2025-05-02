# codealpha_tasks
# 🕵️ Network Sniffer in Python

This Python script is a basic **network packet sniffer** built using the Scapy library. It captures real-time IP packets from the network and prints the source and destination IP addresses along with the protocol type (TCP, UDP, or ICMP).

---

## 📦 Features
- Captures live IP packets from the network.
- Displays source and destination IP addresses.
- Detects and prints the protocol (TCP, UDP, ICMP).
- Analyzes 100 packets per run for performance.

---

## 🛠 Requirements
- Python 3
- Scapy (`pip install scapy`)
- libpcap (`apt-get install -y libpcap-dev`)
- Root or administrator privileges to capture packets

---

## 🚀 Installation
Use the following commands (especially for Linux/Colab environments):


apt-get update
apt-get install -y libpcap-dev
pip install scapy

!apt-get update
!apt-get install -y libpcap-dev

  These commands update the package list and install libpcap, a system library that enables low-level packet capture. They are meant to be run in Linux or Colab environments.
---

!pip install scapy
  Installs the Scapy library, a powerful Python-based tool for network packet analysis and manipulation.
  
---
from scapy.all import sniff
   Imports the sniff function from Scapy, which captures live packets from the network interface.
---
def packet_callback(packet):
Defines a callback function that will be executed every time a new packet is captured.
---
if packet.haslayer("IP"):
Checks if the captured packet includes an IP layer, which most internet traffic does.
---
ip_src = packet["IP"].src
        ip_dst = packet["IP"].dst
        protocol = packet["IP"].proto
Extracts:

ip_src: the source IP address,

ip_dst: the destination IP address,

protocol: a numerical code identifying the protocol used (e.g., 6 = TCP, 17 = UDP).

---
print(f"Source IP: {ip_src} -> Destination IP: {ip_dst} | Protocol: {protocol}")
Prints a summary of the packet, including the source and destination IPs and the protocol number.

---

if packet.haslayer("TCP"):
            print("TCP Protocol detected.")
        elif packet.haslayer("UDP"):
            print("UDP Protocol detected.")
        elif packet.haslayer("ICMP"):
            print("ICMP Protocol detected.")
Checks which transport layer protocol is used in the packet and prints it:

TCP: Reliable connection (e.g., HTTP, HTTPS).

UDP: Unreliable, fast transmission (e.g., video streaming, DNS).

ICMP: Used for error messages (e.g., ping).

---

if packet.haslayer("TCP"):
            print("TCP Protocol detected.")
        elif packet.haslayer("UDP"):
            print("UDP Protocol detected.")
        elif packet.haslayer("ICMP"):
            print("ICMP Protocol detected.")
Checks which transport layer protocol is used in the packet and prints it:

TCP: Reliable connection (e.g., HTTP, HTTPS).

UDP: Unreliable, fast transmission (e.g., video streaming, DNS).

ICMP: Used for error messages (e.g., ping).

---

sniff(prn=packet_callback, store=0, filter="ip", count=100)
Begins capturing packets:

prn=packet_callback: Passes each packet to the packet_callback() function.

store=0: Avoids storing packets in memory to save RAM.

filter="ip": Only captures IP packets.

count=100: Stops after capturing 100 packets.

---

start_sniffing()
Starts the packet sniffer by calling the start_sniffing() function.

--



