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

```bash
apt-get update
apt-get install -y libpcap-dev
pip install scapy


