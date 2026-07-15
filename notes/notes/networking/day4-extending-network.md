# Day 4 - Extending Your Network

## What is port forwarding?

Port forwarding (sometimes called port mapping) is a networking technique used to allow external devices on the internet to access a specific device or service residing inside a private local area network (LAN). Because local devices hide behind a single public IP address via NAT (Network Address Translation), external traffic cannot reach them directly. Port forwarding instructs the router that any incoming traffic hitting a specific public port must be automatically redirected to a designated internal device's private IP address and port.

---

## What is a firewall?

A firewall is a fundamental network security device or software application that monitors and filters incoming and outgoing network traffic based on a defined set of security rules. It acts as a controlled barrier between a trusted, secure internal network and an untrusted external network (such as the internet) to prevent unauthorized access and block malicious payloads.

---

## Stateful firewall

A stateful firewall is an advanced security system that monitors the active context and state of network connections. Instead of looking at packets completely in isolation, it tracks the history of the communication session (such as a TCP three-way handshake) and stores this data in a dynamic **state table**. If a packet arrives that matches an open, established session in the state table, it is automatically allowed through without requiring a separate incoming rule.

---

## Stateless firewall

A stateless firewall is a traditional filtering system that inspects individual packets completely in isolation. It evaluates each packet based strictly on static criteria—such as source/destination IP addresses, ports, and protocol types—against a pre-configured Access Control List (ACL). It possesses no memory of previous traffic or active communication states; it treats every single packet as a brand-new entity.

---

## Stateful vs stateless firewall

| Feature | Stateful Firewall | Stateless Firewall |
| --- | --- | --- |
| **Inspection Scope** | Analyzes packet contents, context, and connection history. | Analyzes individual packet headers completely in isolation. |
| **Tracking Mechanism** | Utilizes a dynamic **state table** to track active sessions. | Does not track sessions; relies strictly on static **Access Control Lists (ACLs)**. |
| **Return Traffic** | Automatically allows safe inbound responses to outbound requests. | Requires manual, explicit rules for both inbound and outbound traffic paths. |
| **Resource Footprint** | Higher memory and CPU usage to actively maintain connection states. | Highly lightweight and incredibly fast due to simple header matching. |
| **Security Profile** | Highly secure; effectively thwarts advanced spoofing and scanning tactics. | Lower security; vulnerable to basic IP spoofing and craftily manipulated packets. |

---

## What is a VPN?

A **Virtual Private Network (VPN)** establishes a secure, encrypted connection (tunnel) over an untrusted public network like the internet. It encapsulates private data packets inside encrypted transport packets, protecting the confidentiality and integrity of data in transit. This ensures that unauthorized third parties cannot eavesdrop on the communication, while masking the user's true public IP address.

---

## What is a router?

A router is a **Layer 3 (Network Layer)** hardware device responsible for forwarding data packets between completely separate networks. By reading the logical destination IP address of incoming packets and referencing its internal routing table, a router determines the most efficient path across networks to ensure data successfully transitions from its source to its ultimate remote destination.

---

## What is a switch?

A switch is a **Layer 2 (Data Link Layer)** hardware device used to connect multiple individual endpoints (computers, printers, servers) together within the **same local network (LAN)**. It inspects the physical destination MAC addresses within incoming frames to deliver data strictly to the exact physical port where the target device is connected, maximizing local bandwidth efficiency.

---

## Router vs switch

The fundamental distinction rests on their operational boundaries: A **switch** connects devices locally to build a single network at Layer 2, using MAC addresses to pass traffic inside that environment. A **router** connects entirely separate networks together at Layer 3, using IP addresses to route data globally across those boundaries.

---

## Three things I found difficult

1. **Visualizing the State Table:** Grasping exactly how a stateful firewall dynamically updates its state table in real-time when handling hundreds of simultaneous multi-threaded TCP connections.
2. **Port Forwarding vs. DMZ:** Differentiating the precise security implications of configuring strict single-port forwarding versus exposing an entire host via a Demilitarized Zone (DMZ) setup.
3. **VPN Encapsulation Overhead:** Conceptualizing how the addition of outer VPN IP headers and encryption trailers affects packet MTU (Maximum Transmission Unit) sizes and causes packet fragmentation.

---

## Interview questions

### What is a firewall?

> "A firewall is a network security control designed to monitor, filter, and restrict incoming and outgoing network traffic based on established security rules. It acts as the primary perimeter defense line, separating a secure internal network from untrusted external spaces like the internet."

### What is the difference between a stateful and stateless firewall?

> "The key difference is context awareness. A stateful firewall tracks the operational state and history of active network connections using a dynamic state table, allowing return traffic automatically. A stateless firewall inspects every packet completely in isolation against static access lists, meaning it has no memory of whether a packet is part of an ongoing, valid connection."

### What is a VPN?

> "A VPN, or Virtual Private Network, extends a private network across a public infrastructure by creating an encrypted communication tunnel. It ensures data confidentiality and integrity in transit, protecting sensitive communication from interception while hiding the user's actual external IP address."

### What is the difference between a router and a switch?

> "A switch operates at Layer 2 of the OSI model to connect multiple devices together inside the same local network using physical MAC addresses. A router operates at Layer 3 to connect completely different networks together, passing data packets between those networks using logical IP addresses."

### What is port forwarding?

> "Port forwarding is a configuration on a network router that directs external incoming traffic targeting a specific public port directly to an internal device's private IP address and port. It allows external internet users to access specific services—like web servers or remote desktops—that are hosted inside a private, NAT-protected local network."

---

## What I completed

* Completed Extending Your Network on TryHackMe.
* Completed the firewall and network simulator exercises.
* Reviewed networking fundamentals.
