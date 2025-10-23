# Packet Forwarding and Next-Hop Routing Simulation

## 🌐 Project Overview
This project demonstrates **packet forwarding and next-hop routing** using **Cisco Packet Tracer**. It helps visualize how packets travel through routers and how routing tables determine the next hop to reach remote networks.

### Step-by-step simulation of the packet flow in our network topology:
https://github.com/user-attachments/assets/5fa203b0-1d80-4b2f-b698-2b28cd401ce2

### 🧱 Topology
PC0 ⇨ R1 ⇨ R2 ⇨ PC1


### Networks
| Link      | Network        | Subnet Mask       | Devices & IPs                  |
|-----------|----------------|-----------------|--------------------------------|
| PC0 ↔ R1  | 192.168.10.0/24 | 255.255.255.0   | PC0: 192.168.10.2, R1: 192.168.10.1 |
| R1 ↔ R2  | 10.0.0.0/8      | 255.0.0.0       | R1: 10.0.0.1, R2: 10.0.0.2           |
| R2 ↔ PC1 | 172.16.5.0/24   | 255.255.255.0   | R2: 172.16.5.1, PC1: 172.16.5.2     |

---

### ⚙️ Steps Performed:

#### 1️⃣ Device Setup
- Added 2 PCs and 2 routers (Cisco 2901/2911).  
- Connected using **Copper Straight-Through cables**.

#### 2️⃣ IP Configuration
**PCs:**
- PC0: IP 192.168.10.2, Subnet 255.255.255.0, Gateway 192.168.10.1  
- PC1: IP 172.16.5.2, Subnet 255.255.255.0, Gateway 172.16.5.1  

**Routers:**
- R1 Interfaces:  
  - G0/0 → 192.168.10.1/24  
  - G0/1 → 10.0.0.1/8  
- R2 Interfaces:  
  - G0/0 → 10.0.0.2/8  
  - G0/1 → 172.16.5.1/24  
- Command used: `no shutdown` to activate interfaces.

#### 3️⃣ Connectivity Verification
- **Direct ping tests:**  
  - PC0 ↔ R1 ✅  
  - R1 ↔ R2 ✅  
  - R2 ↔ PC1 ✅  

#### 4️⃣ Static Routing Configuration
**R1 → PC1 network:**  

#### R2 → PC1 network:
ip route 192.168.10.0 255.255.255.0 10.0.0.1

#### End-to-End Test
PC1 → PC2 ping successful ✅
Packet path: PC0 → R1 → R2 → PC1

#### Routing Table Verification
### R1 Routing Table
S 172.16.5.0 [1/0] via 10.0.0.2
C 192.168.10.0 is directly connected
C 10.0.0.0 is directly connected

#### R2 Routing Table
S 192.168.10.0 [1/0] via 10.0.0.1
C 10.0.0.0 is directly connected
C 172.16.5.0 is directly connected

#### 🎬 Simulation Mode
1) Use Simulation Mode in Packet Tracer to visualize packet movement.
2) Add a Simple PDU from PC0 → PC1.
3) Observe headers, source/destination IPs, and routing decisions at each router.

#### 🧠 Key Learnings
1) Next-Hop Routing: Routers forward packets using next-hop IPs in routing tables.
2) Direct vs Remote Networks: Directly connected networks are automatically known; others require static/dynamic routes.
3) Routing Tables as GPS: Routers consult the routing table to decide the path for every packet.
4) Packet Visualization: Simulation mode helps understand packet flow, headers, and address changes.

#### 💡 Future Enhancements

- Add more routers and networks to simulate larger topologies.
- Experiment with dynamic routing protocols like RIP, OSPF, or EIGRP.
- Include Wireshark captures for deeper packet analysis.

#### 🤝 Contributing

🚀 I'm thrilled to share my latest project with you on GitHub! If you find it helpful, inspiring, or just plain awesome, I’d be incredibly grateful if you could ⭐ star the repository!

#### 📬 Contact:

For any questions, suggestions or collaboration opportunities, feel free to reach out:

[![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:adityapateriya7986@gmail.com)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aditya-pateriya7781/)
