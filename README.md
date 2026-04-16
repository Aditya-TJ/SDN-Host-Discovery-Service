# 🚀 SDN Host Discovery Service using Mininet & Ryu

A Software Defined Networking (SDN) project that implements a **Host Discovery Service** using the **Ryu Controller** and **Mininet**. The controller dynamically detects connected hosts, learns host information, and maintains a live host database.

---

## 📌 Project Objective

To build an SDN-based host discovery mechanism that automatically identifies hosts connected to the network and stores:

* MAC Address
* IP Address
* Switch ID
* Port Number

This demonstrates centralized SDN control and dynamic network visibility.

---

## 🛠️ Tech Stack

* **Ubuntu Linux**
* **Mininet**
* **Ryu Controller**
* **Open vSwitch**
* **Python**
* **Wireshark**

---

## 🌐 Network Topology

### Scenario 1: 3 Hosts

```text
h1 ---\
h2 ---- s1
h3 ---/
```

### Scenario 2: 4 Hosts (Dynamic Update)

```text
h1 ---\
h2 ----\
h3 ----- s1
h4 ----/
```

---

## ⚙️ Installation & Setup

### 1️⃣ Start Ryu Controller

```bash
~/.local/bin/ryu-manager host_discovery.py
```

### 2️⃣ Run Mininet (3 Hosts)

```bash
sudo mn --topo single,3 --controller remote
```

### 3️⃣ Test Network

```bash
pingall
nodes
net
dump
iperf
```

### 4️⃣ Dynamic Host Update (4 Hosts)

```bash
exit
sudo mn -c
sudo mn --topo single,4 --controller remote
pingall
```

---

## 🧠 Core Functionalities

✅ Detects newly connected hosts automatically
✅ Maintains host database dynamically
✅ Learns MAC-to-port mapping
✅ Handles Packet-In events
✅ Forwards packets intelligently
✅ Supports topology changes

---

## 📊 Validation & Results

### ✔ Scenario 1

* 3 hosts discovered successfully
* Ping successful
* Controller logs updated

### ✔ Scenario 2

* Topology expanded to 4 hosts
* New host auto-detected
* Network remained functional

---

## 📈 Performance Analysis

### Latency

```bash
pingall
```

### Throughput

```bash
iperf
```

### Flow Table Inspection

```bash
sudo ovs-ofctl -O OpenFlow13 dump-flows s1
```

### Packet Capture

Observed using Wireshark:

* ARP Packets
* ICMP Packets
* OpenFlow Messages

---

## 📂 Project Structure

```text
SDN-Host-Discovery-Service/
│── host_discovery.py
│── README.md
└── screenshots/
```

---

## 📸 Proof of Execution

Screenshots available in the `screenshots/` folder:

* Controller Logs
* Ping Results
* Wireshark Captures
* Flow Tables
* Throughput Results

---

## 🎯 Conclusion

The Host Discovery Service was successfully implemented using Mininet and Ryu Controller. The controller dynamically identified hosts, maintained accurate host records, and handled topology changes efficiently.

This project highlights the power of SDN through centralized control, programmability, and real-time network awareness.

---

## 🔮 Future Enhancements

* GUI Dashboard
* Real-time Host Join/Leave Alerts
* Traffic Analytics
* Security Policy Integration

---

## 👨‍💻 Author

**Aditya TJ**

---

## 📚 References

* Mininet Documentation
* Ryu SDN Framework
* OpenFlow Specification
.
