### What is a CIDR Block?

**CIDR** stands for **Classless Inter-Domain Routing**. A **CIDR block** is a method for allocating IP addresses and routing Internet Protocol packets. It is written in the format:

```
<IP_address>/<prefix_length>
```

Example:

```
192.168.0.0/24
```

---

### Key Components:

1. **IP Address**: A 32-bit (IPv4) or 128-bit (IPv6) numerical label (e.g., 192.168.0.0).
2. **Prefix Length**: The number after the `/`, such as `/24`, indicates how many bits are **fixed** for the **network portion**.

---

### CIDR vs Traditional Classes:

| Class | Default Subnet Mask | CIDR Notation | IP Range                    |
| ----- | ------------------- | ------------- | --------------------------- |
| A     | 255.0.0.0           | /8            | 0.0.0.0 – 127.255.255.255   |
| B     | 255.255.0.0         | /16           | 128.0.0.0 – 191.255.255.255 |
| C     | 255.255.255.0       | /24           | 192.0.0.0 – 223.255.255.255 |

CIDR breaks this rigid class system and allows more flexible subnetting.

---

### Why CIDR is Used:

* **Efficient IP allocation** (e.g., give a company only the addresses they need).
* **Reduces routing table size** (supernetting).
* **Allows subnetting of any size** (e.g., /29 for 8 IPs, /30 for 4 IPs, etc.).

---

### CIDR Block Range Calculation

#### Formula:

* Total IPs = 2^(32 - prefix length)

#### Example:

For `192.168.1.0/24`:

* Prefix length = 24 → Network bits = 24, Host bits = 8
* 2^8 = **256 IP addresses** (from 192.168.1.0 to 192.168.1.255)

#### Another Example:

For `10.0.0.0/16`:

* Prefix = 16 → Host bits = 16
* 2^16 = **65,536 IP addresses**

---

### Common CIDR Notations:

| CIDR | # of IPs   | Usable IPs | Subnet Mask     |
| ---- | ---------- | ---------- | --------------- |
| /30  | 4          | 2          | 255.255.255.252 |
| /29  | 8          | 6          | 255.255.255.248 |
| /28  | 16         | 14         | 255.255.255.240 |
| /24  | 256        | 254        | 255.255.255.0   |
| /16  | 65,536     | 65,534     | 255.255.0.0     |
| /8   | 16,777,216 | 16,777,214 | 255.0.0.0       |

> *Usable IPs* = Total IPs - 2 (for network and broadcast addresses)

---

### Where CIDR is Used:

* **Cloud services (AWS, Azure, GCP)** for defining **VPCs**, **subnets**, **security groups**.
* **Routers** to summarize and route multiple IP addresses efficiently.
* **Subnetting** and **supernetting** tasks in enterprise networks.
