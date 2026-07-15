# Day 3 - OSI Model and Packets

## Seven OSI layers

1. **Physical** - Transmits raw, unstructured bit streams over physical media (cables, fiber, radio waves).
2. **Data Link** - Packages raw bits into **frames**, handles physical addressing via **MAC addresses**, and detects local errors.
3. **Network** - Handles logical addressing via **IP addresses** and routes data packets between completely different networks.
4. **Transport** - Manages end-to-end communication control, data segmentation, and reliability using protocols like **TCP** and **UDP** via **ports**.
5. **Session** - Establishes, coordinates, and terminates persistent communication sessions between applications.
6. **Presentation** - Translates, encrypts, and compresses data, formatting it so the application layer can properly read it.
7. **Application** - The network service layer directly interacting with user-facing software applications (like a web browser).

---

## What is encapsulation?

Encapsulation is the process where data moves down the OSI stack, and each layer wraps the incoming data payload with its own control information—called **headers** (and sometimes trailers). It works like placing a letter inside an envelope, placing that envelope inside a shipping box, and putting that box into a delivery truck.

---

## What is a packet?

A packet is the standard unit of data formatted at **Layer 3 (Network Layer)** of the OSI model. It consists of the upper-layer data wrapped in an IP header containing the source and destination logical **IP addresses** used for global routing.

---

## What is a frame?

A frame is the unit of data formatted at **Layer 2 (Data Link Layer)**. It encapsulates the Layer 3 IP packet by adding a hardware header containing the source and destination physical **MAC addresses**, alongside a trailer to check for transmission corruption.

---

## Packet vs frame

| Feature | Packet | Frame |
| --- | --- | --- |
| **OSI Layer** | Layer 3 (Network Layer) | Layer 2 (Data Link Layer) |
| **Addressing** | Logical IP Addresses | Physical MAC Addresses |
| **Primary Device** | Evaluated and sent by **Routers** | Evaluated and sent by **Switches** |
| **Scope** | Travels globally across different networks | Travels locally within a single network segment |

---

## TCP vs UDP

### TCP (Transmission Control Protocol)

* **Connection-Oriented:** Requires a formal connection setup (the three-way handshake) before any data is sent.
* **Reliable Delivery:** Guarantees that all segments arrive completely intact, error-free, and in the correct sequence through tracking and acknowledgments.
* **Higher Overhead:** Slower data flow due to heavy error-checking features, flow control boundaries, and larger headers.

### UDP (User Datagram Protocol)

* **Connectionless:** Sends data out instantly without verifying if the receiving host is active or ready.
* **Best-Effort Delivery:** Unreliable; it does not check if data segments drop, corrupt, or arrive completely out of sequence.
* **Low Overhead:** Extremely fast and lightweight because it cuts out all flow control and acknowledgment overhead—ideal for gaming and video streaming.

---

## TCP three-way handshake

1. **SYN (Synchronize)** - The client sends a packet with the `SYN` flag enabled to request a connection and establish its initial sequence number.
2. **SYN-ACK (Synchronize-Acknowledgment)** - The server responds with both `SYN` and `ACK` flags enabled, acknowledging the client's request while sending its own sequence number.
3. **ACK (Acknowledgment)** - The client transmits a final `ACK` packet to confirm the server's parameters, officially opening the connection for data flow.

---

## Common ports

* **Port 22** - **SSH (Secure Shell)** — Used for secure, encrypted remote command-line access.
* **Port 25** - **SMTP (Simple Mail Transfer Protocol)** — Used for sending emails between mail servers.
* **Port 53** - **DNS (Domain Name System)** — Maps human-readable domain names to routable IP addresses.
* **Port 80** - **HTTP (Hypertext Transfer Protocol)** — Used for transmitting standard, unencrypted web traffic.
* **Port 443** - **HTTPS (Hypertext Transfer Protocol Secure)** — Used for transmitting secure, encrypted web traffic via SSL/TLS.

---

## Three things I found difficult

1. **Remembering Layer 2:** Forgetting the **Data Link** layer or mixing it up with surrounding layers when performing quick memory dumps.
2. **Visualizing Encapsulation in Action:** Tracking how headers are added or stripped away seamlessly as data shifts between routers and local switches.
3. **Port Association:** Keeping various service ports clearly separated without accidentally blending baseline infrastructure protocols together.

---

## Interview questions

### Explain the OSI model simply.

> "The OSI model is a 7-layer theoretical framework that standardizes how data travels across a network from physical wires up to software applications. By breaking networking into distinct layers, it ensures different vendor technologies can communicate, while helping security teams pinpoint exactly where an exploit or failure is taking place."

### What is the difference between TCP and UDP?

> "The core difference comes down to reliability versus speed. TCP is connection-oriented and guarantees all data arrives completely intact and in the right order using acknowledgments and a handshake. UDP is connectionless and shifts focus entirely to raw speed, sending data instantly with a best-effort approach and zero delivery confirmations."

### What is the TCP three-way handshake?

> "It is the structural mechanism TCP uses to establish a reliable connection before data transfer starts. It follows a three-step flag sequence: First, the client sends a `SYN` packet to initiate the connection. Second, the server replies with a `SYN-ACK` packet to acknowledge the request. Finally, the client sends an `ACK` packet back to confirm, opening the connection."

### Which port does HTTPS use?

> "HTTPS uses **Port 443** by default to encrypt web traffic using SSL/TLS, whereas unencrypted HTTP relies on Port 80."

### At which OSI layer does a router mainly operate?

> "A router operates primarily at **Layer 3 (the Network Layer)** because its primary objective relies on reading logical IP addresses to evaluate paths and forward packets between separate networks."
