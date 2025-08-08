## **The OSI Model (Open Systems Interconnection) – 7 Layers**

The **OSI Model** helps professionals understand how different components of a network interact during data transmission. It breaks down the communication process into **7 layers**, each with specific functions.

---

### **Layer 7 – Application Layer**

**What it does:**  
Interacts directly with user applications that access the network.

**Real-world examples:**

- **Web browsing** → HTTP/HTTPS
    
- **Emailing** → SMTP, IMAP
    
- **DNS requests** → Translates `www.example.com` to IP
    

**Tools or protocols involved:**  
HTTP, HTTPS, FTP, SMTP, DNS, Telnet

---

### **Layer 6 – Presentation Layer**

**What it does:**  
Formats and transforms data for the application layer. Handles **encryption, compression, and data translation**.

**Real-world examples:**

- **HTTPS encryption** using **SSL/TLS**
    
- **JPEG image compression** before sending
    
- **Translating character sets** (e.g., ASCII to Unicode)
    

**Tools or protocols involved:**  
SSL/TLS, MPEG, JPEG, ASCII, EBCDIC

---

### **Layer 5 – Session Layer**

**What it does:**  
Manages the start, maintenance, and end of **communication sessions** between devices.

**Real-world examples:**

- **Video conferencing tools** (Zoom, Skype) maintaining an ongoing session
    
- Handling **login sessions** to a remote server
    

**Functions:**

- Authentication
    
- Checkpointing (resume from last known good state)
    
- Session termination
    

---

### **Layer 4 – Transport Layer**

**What it does:**  
Delivers data **end-to-end** and ensures **reliable transmission** using segmentation and reassembly.

**Real-world examples:**

- **TCP** ensures your YouTube video buffers smoothly without data loss
    
- **UDP** used for faster but unreliable data in **gaming or voice calls**
    

**Protocols used:**

- TCP (Transmission Control Protocol)
    
- UDP (User Datagram Protocol)
    

---

### **Layer 3 – Network Layer**

**What it does:**  
Handles **routing** and **logical addressing** (IP addresses). Sends data between **different networks**.

**Real-world examples:**

- Your data is routed through **routers** to reach a web server in another country
    
- **IP packets** are assigned source and destination addresses
    

**Protocols involved:**

- IP (IPv4, IPv6)
    
- ICMP (ping)
    
- Routers work at this layer
    

---

### **Layer 2 – Data Link Layer**

**What it does:**  
Manages communication **within the same local network** using **MAC addresses**. Ensures error-free delivery between two directly connected devices.

**Real-world examples:**

- A **switch** sending data from one computer to another on the same LAN
    
- Your **Wi-Fi adapter** communicating with the router
    

**Protocols involved:**

- Ethernet, ARP, PPP, HDLC
    

---

### **Layer 1 – Physical Layer**

**What it does:**  
Transmits raw **bits (0s and 1s)** over a physical medium. Represents the **hardware** of the network.

**Real-world examples:**

- **Cables** (Ethernet, fiber optic, coaxial)
    
- **Hubs, modems, network interface cards**
    
- **Wi-Fi signals**, light pulses in fiber, or electrical signals on copper
    

**Mediums involved:**

- Electrical (Ethernet cables)
    
- Optical (Fiber optics)
    
- Radio (Wi-Fi)
    

---

## **OSI vs. TCP/IP**

| OSI Layer        | TCP/IP Equivalent | Key Difference                      |
| ---------------- | ----------------- | ----------------------------------- |
| Application (7)  | Application       | Covers user applications            |
| Presentation (6) | Application       | Combined into one layer in TCP/IP   |
| Session (5)      | Application       | Combined into one layer in TCP/IP   |
| Transport (4)    | Transport         | Same                                |
| Network (3)      | Internet          | IP routing in both models           |
| Data Link (2)    | Network Access    | TCP/IP combines Layer 2 and Layer 1 |
| Physical (1)     | Network Access    | TCP/IP combines Layer 2 and Layer 1 |