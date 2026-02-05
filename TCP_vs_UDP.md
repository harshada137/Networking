## 🌐 TCP vs UDP – Transport Layer Protocols

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) operate at the **Transport Layer (Layer 4)** of the OSI model. They define **how data is transmitted between systems** over a network.

---

### 🔁 Comparison Table

| Feature            | TCP                       | UDP                     |
| ------------------ | ------------------------- | ----------------------- |
| Connection Type    | Connection-oriented       | Connectionless          |
| Reliability        | Guaranteed delivery       | No delivery guarantee   |
| Data Order         | Maintains order           | No ordering             |
| Error Checking     | Yes (with retransmission) | Yes (no retransmission) |
| Flow Control       | Yes                       | No                      |
| Congestion Control | Yes                       | No                      |
| Speed              | Slower                    | Faster                  |
| Overhead           | High                      | Low                     |
| Handshake          | 3-way handshake           | No handshake            |
| Data Loss Handling | Retransmits lost packets  | Drops packets           |
| Use Case Priority  | Accuracy                  | Speed                   |

---

### 📦 TCP – Reliable & Ordered

TCP ensures:

* Data arrives **completely**
* Data arrives **in order**
* Lost packets are **retransmitted**

#### 🔐 TCP 3-Way Handshake

1. **SYN**
2. **SYN-ACK**
3. **ACK**

This guarantees a stable connection before data transfer.

#### 📌 Common TCP Use Cases

* HTTP / HTTPS
* SSH
* FTP
* SMTP
* Database connections (MySQL, PostgreSQL)

---

### ⚡ UDP – Fast & Lightweight

UDP:

* Sends data **without establishing a connection**
* Does **not wait** for acknowledgements
* Prioritizes **speed over reliability**

#### 📌 Common UDP Use Cases

* DNS
* VoIP (calls, video meetings)
* Online gaming
* Live streaming
* DHCP

---

### 🧠 DevOps / Cloud Perspective

| Scenario                  | Preferred Protocol | Reason                 |
| ------------------------- | ------------------ | ---------------------- |
| Web applications          | TCP                | Reliable data transfer |
| Kubernetes health checks  | TCP                | Accurate status        |
| Video streaming           | UDP                | Low latency            |
| DNS resolution            | UDP                | Fast lookups           |
| Microservices (HTTP APIs) | TCP                | Data integrity         |

---

### 🐳 Docker & Kubernetes Insight

* **Service Type (NodePort / ClusterIP)** → Supports both TCP & UDP
* **Ingress Controllers** → Mostly TCP (HTTP/HTTPS)
* **CNI plugins** → Optimize TCP performance heavily
* **UDP apps** need explicit port configuration

---

### 🎯 Interview One-Liner

> **TCP is reliable but slow; UDP is fast but unreliable. Choose based on whether accuracy or speed matters more.**

