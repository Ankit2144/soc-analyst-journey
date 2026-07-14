# Day 2 - Networking Basics

## What is a network?

A network is a collection of interconnected devices—such as computers, servers, switches, and routers—that communicate with one another to share resources, exchange data, and access the internet. It can range from a tiny Local Area Network (LAN) in a home office to the global internet.

---

## What is an IP address?

An **Internet Protocol (IP) address** is a logical numerical identifier assigned to every device participating in a network. Operating at **Layer 3 (Network Layer)** of the OSI model, it acts like a digital mailing address, allowing data packets to be routed across entirely separate networks to find the correct destination.

* **IPv4:** Written in dotted-decimal format (e.g., `192.168.1.1`).
* **IPv6:** A larger alphanumeric format introduced to replace exhausting IPv4 spaces (e.g., `2001:db8::ff00:42:8329`).

---

## What is a MAC address?

A **Media Access Control (MAC) address** is a unique, 12-character hexadecimal physical identifier burned permanently into a device's Network Interface Card (NIC) during manufacturing (e.g., `00:1A:2B:3C:4D:5E`). Operating at **Layer 2 (Data Link Layer)**, it ensures that data frames traveling through a local physical environment are delivered to the exact hardware interface they belong to.

---

## IP address vs MAC address

| Feature | IP Address | MAC Address |
| --- | --- | --- |
| **Type** | Logical address. | Physical address. |
| **OSI Layer** | Layer 3 (Network). | Layer 2 (Data Link). |
| **Permanence** | Temporary/Changeable (assigned by network). | Permanent (burned into the hardware component). |
| **Scope** | Global or local network routing. | Local network segment delivery only. |

---

## What does ping do?

**Ping** is a command-line network diagnostic utility used to test whether a specific target host is reachable across an IP network. It works by sending **ICMP (Internet Control Message Protocol) Echo Request** packets to the destination and listening for an **ICMP Echo Reply**. It provides two crucial pieces of data:

* Whether the remote host is alive/active.
* The round-trip time (latency) measured in milliseconds, alongside any packet loss.

---

## What is DHCP?

**Dynamic Host Configuration Protocol (DHCP)** is a network management protocol that automatically provisions IP addresses and other critical configuration parameters to devices joining a network. Instead of a network administrator manually typing static settings into every machine, a DHCP server automatically leases out:

* A unique IP address
* A Subnet Mask (defines network/host portions)
* A Default Gateway (the router path to leave the network)
* DNS Server addresses

---

## What is ARP?

**Address Resolution Protocol (ARP)** is the essential operational bridge that maps a known logical Layer 3 IP address to a physical Layer 2 MAC address within a local area network. When a computer wants to send data to an IP on its local segment, it checks its internal ARP cache. If it doesn't know the hardware target, it sends an **ARP Broadcast Request** asking: *"Who owns this IP? Tell me your MAC address."*

---

## Router vs switch

While both are foundational network boxes, they have completely distinct directives:

* **Switch:** Connects multiple individual devices together within the **same local network**. Basic Layer 2 switches use MAC addresses to forward frames locally, while advanced Layer 3 switches can leverage IP routing and create isolated **VLANs** to split up departments securely.
* **Router:** Connects completely **different networks together**. Operating strictly at Layer 3, a router tracks multiple external paths and uses routing protocols to select the most optimal path for traffic based on speed, path length, and line reliability.

---

## Three things I found difficult

1. **Visualizing Packet Encapsulation:** Remembering how an IP packet gets wrapped inside a Layer 2 hardware frame, and how that frame changes at every router hop while the IP packet stays the same.
2. **Subnet Mask Calculations:** Calculating network boundaries, broadcast addresses, and usable host ranges quickly using binary logic.
3. **ARP vs. DNS Ambiguity:** Keeping it clear that DNS maps names to IPs globally, whereas ARP maps IPs to physical MAC addresses locally.

---

## Interview questions

### What is an IP address?

> "An IP address is a logical identifier assigned to a device on a network, operating at Layer 3 of the OSI model. Its primary purpose is to provide a uniquely routable identity so data packets can cross different networks and reach the correct destination host."

### What is the difference between an IP address and a MAC address?

> "The primary difference is their layer of operation and permanence. An IP address is a logical, changeable address operating at Layer 3 used for routing data between networks. A MAC address is a physical, unchangeable hexadecimal identifier burned into the network card at Layer 2, used to deliver data packets locally inside a single network segment."

### What is DHCP?

> "DHCP stands for Dynamic Host Configuration Protocol. It is a service that automatically assigns essential network configurations—like IP addresses, subnet masks, default gateways, and DNS servers—to devices the moment they connect to the network, eliminating manual setup errors."

### What is ARP?

> "ARP, or Address Resolution Protocol, acts as the link between Layer 3 and Layer 2. It maps a known IP address to its corresponding physical MAC address on a local network, allowing devices to construct the physical frames required to transmit data locally."

### What does ping do?

> "Ping is a utility used to verify network connectivity. It transmits ICMP Echo Requests to a specific destination IP or domain and waits for an Echo Reply. It helps an analyst verify if a host is alive, while detailing network latency and packet loss rates."
