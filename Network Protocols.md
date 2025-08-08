## **1. TCP (Transmission Control Protocol)**

**Purpose**: Ensures reliable, ordered, and error-checked data delivery between applications.

### **Key Features**:

- Connection-oriented (3-way handshake)
    
- Flow control (adjusts speed based on receiver capacity)
    
- Error recovery (retransmits lost packets)
    
- Used by HTTP, FTP, SSH, etc.
    

### **Practical Example: Loading a Webpage**

1. **3-Way Handshake** (Establishes connection):
    
    - Client → Server: `SYN` (Synchronize)
        
    - Server → Client: `SYN-ACK` (Acknowledgment)
        
    - Client → Server: `ACK` (Connection established)
        
2. **Data Transfer**:
    
    - Browser sends HTTP request (`GET / HTTP/1.1`).
        
    - Server responds with webpage data.
        
3. **Connection Termination** (4-way handshake).
    

---

## **2. ARP (Address Resolution Protocol)**

**Purpose**: Maps an **IP address** to a **MAC address** (for local network communication).

### **How ARP Works**:

1. Device wants to send data to `192.168.1.5` but doesn’t know its MAC address.
    
2. Sends an **ARP Request** (broadcast):  
    _"Who has 192.168.1.5? Tell 192.168.1.10 (my IP)"_
    
3. The correct device replies with an **ARP Reply**:  
    _"192.168.1.5 is at MAC 00:1A:2B:3C:4D:5E"_
    
4. The sender caches this mapping in its **ARP table**.
    

### **Practical Example: Connecting to a Local Printer**

- Your PC (`192.168.1.10`) wants to print but doesn’t know the printer’s MAC.
    
- ARP finds the printer’s MAC (`00:1A:2B:3C:4D:5E`).
    
- Now, your PC can send print jobs directly to the printer.
    

---

## **3. HTTPS (Hypertext Transfer Protocol Secure)**

**Purpose**: Encrypted version of HTTP for secure web browsing.

### **How HTTPS Works**:

1. **TCP Connection**: Establishes a connection (3-way handshake).
    
2. **TLS Handshake** (Encryption Setup):
    
    - Client sends `ClientHello` (supported encryption methods).
        
    - Server responds with `ServerHello` (selected method + **SSL certificate**).
        
    - Key exchange (asymmetric encryption → symmetric session key).
        
3. **Encrypted Data Transfer**:
    
    - All HTTP data (login details, credit card info) is encrypted.
        

### **Practical Example: Online Banking**

- You visit `https://bank.com`.
    
- Browser verifies the bank’s SSL certificate.
    
- All communication (login, transactions) is encrypted.
    
- Without HTTPS, hackers could steal your data.
    

---

## **4. DNS (Domain Name System)**

**Purpose**: Translates **domain names (e.g., google.com)** into **IP addresses (e.g., 142.250.190.46)**.

### **How DNS Works**:

1. **Browser Checks Cache**: "Have I visited google.com recently?"
    
2. **OS/Resolver Cache**: If not, asks the OS (which may check `/etc/hosts` or a local DNS resolver).
    
3. **Recursive DNS Query** (if not cached):
    
    - Asks **ISP’s DNS Server** → If unknown, queries **Root DNS**.
        
    - Root DNS points to **.com TLD (Top-Level Domain) Server**.
        
    - TLD points to **Google’s Authoritative DNS Server**.
        
    - Returns the IP (`142.250.190.46`).
        
4. **Browser Connects** to the IP via TCP.
    

### **Practical Example: Visiting a Website**

- You type `facebook.com` → DNS finds `157.240.229.35`.
    
- Without DNS, you’d have to remember IPs for every website!

---

## **1. Transmission Control Protocol (TCP)**

### **Purpose**

- **Reliable, connection-oriented** data transmission.
    
- Ensures **ordered delivery, error correction, and flow control**.
    

### **How TCP Works**

1. **3-Way Handshake** (Connection Establishment):
    
    - **SYN** → Client sends a synchronization request.
        
    - **SYN-ACK** → Server acknowledges and responds.
        
    - **ACK** → Client confirms, establishing a connection.
        
2. **Data Transfer**:
    
    - Segments are numbered (**sequence numbers**) for reassembly.
        
    - **ACKs** confirm received data; lost packets are retransmitted.
        
3. **4-Way Handshake** (Connection Termination):
    
    - FIN → ACK → FIN → ACK (graceful shutdown).
        

### **Practical Example: Web Browsing**

- When you visit `google.com`:
    
    1. Browser initiates TCP connection (SYN, SYN-ACK, ACK).
        
    2. HTTP request (`GET /`) sent over TCP.
        
    3. Server responds with webpage data.
        
    4. Connection closes after transfer.
        

### **Security Risks & Mitigations**

|Risk|Description|Mitigation|
|---|---|---|
|**TCP Hijacking**|Attacker predicts sequence numbers to take over a session.|Use **randomized sequence numbers**, **firewalls**.|
|**SYN Flood Attack**|Overwhelms server with half-open connections.|**SYN cookies**, rate limiting.|

---

## **2. Address Resolution Protocol (ARP)**

### **Purpose**

- Maps **IP addresses** to **MAC addresses** (local network).
    
- Essential for **Layer 2 (Ethernet/Wi-Fi) communication**.
    

### **How ARP Works**

1. **ARP Request (Broadcast)**:
    
    - _"Who has 192.168.1.1? Tell 192.168.1.2"_ (sent to `FF:FF:FF:FF:FF:FF`).
        
2. **ARP Reply (Unicast)**:
    
    - _"192.168.1.1 is at 00:1A:2B:3C:4D:5E"_.
        
3. **ARP Cache**:
    
    - Stores mappings temporarily (~2 mins to 2 hours).
        

### **Practical Example: Connecting to a Router**

- Your PC (`192.168.1.2`) wants to send data to the router (`192.168.1.1`).
    
- ARP finds the router’s MAC address (`00:1A:2B:3C:4D:5E`).
    
- Data is then sent via Ethernet frames.
    

### **Security Risks & Mitigations**

|Risk|Description|Mitigation|
|---|---|---|
|**ARP Poisoning (Spoofing)**|Attacker sends fake ARP replies to redirect traffic (MITM).|**Dynamic ARP Inspection (DAI)**, static ARP entries.|
|**MAC Flooding**|Overflows switch’s MAC table, forcing broadcast mode.|**Port security**, MAC limiting.|

---

## **3. Hypertext Transfer Protocol Secure (HTTPS)**

### **Purpose**

- **Encrypted HTTP** using **TLS/SSL**.
    
- Protects data integrity, confidentiality, and authenticity.
    

### **How HTTPS Works (TLS Handshake)**

1. **ClientHello** → Browser sends supported encryption methods.
    
2. **ServerHello** → Server selects cipher suite + sends **SSL certificate**.
    
3. **Key Exchange** → Asymmetric encryption (RSA/ECDHE) establishes a **session key**.
    
4. **Encrypted Data Transfer** → Symmetric encryption (AES) secures HTTP traffic.
    

### **Practical Example: Online Banking**

- You log in to `https://bank.com`:
    
    1. Browser verifies bank’s SSL certificate.
        
    2. Establishes encrypted session (AES-256).
        
    3. All login/transaction data is encrypted.
        

### **Security Risks & Mitigations**

|Risk|Description|Mitigation|
|---|---|---|
|**Man-in-the-Middle (MITM)**|Attacker intercepts unencrypted HTTP traffic.|**Always use HTTPS (HSTS enforcement)**.|
|**Expired/Invalid Certificates**|Fake certificates trick users.|**Certificate Transparency (CT)**, browser warnings.|

---

## **4. Domain Name System (DNS)**

### **Purpose**

- Translates **domain names (e.g., google.com)** → **IP addresses (e.g., 142.250.190.46)**.
    

### **How DNS Works**

1. **Browser Cache** → Checks if `google.com` is cached.
    
2. **OS/Resolver Cache** → Queries `/etc/hosts` or local DNS.
    
3. **Recursive Query** (if not cached):
    
    - **Root DNS** (.) → **TLD (.com)** → **Authoritative DNS (Google’s server)**.
        
4. **Response** → Returns IP (`142.250.190.46`).
    

### **Practical Example: Visiting a Website**

- You type `facebook.com` → DNS resolves to `157.240.229.35`.
    
- Without DNS, you’d need to remember IPs!
    

### **Security Risks & Mitigations**

|Risk|Description|Mitigation|
|---|---|---|
|**DNS Spoofing (Cache Poisoning)**|Fake DNS responses redirect users to malicious sites.|**DNSSEC (DNS Security Extensions)**.|
|**DNS Amplification Attack**|DDoS using open DNS resolvers.|**Rate limiting**, disabling open recursion.|

---

## **5. Other Key Protocols**

### **UDP (User Datagram Protocol)**

- **Connectionless, fast** (no handshake).
    
- Used in **DNS queries, VoIP, video streaming**.
    
- **Risk**: No error recovery → **UDP flood attacks**.
    

### **ICMP (Internet Control Message Protocol)**

- **Network diagnostics** (`ping`, `traceroute`).
    
- **Risk**: **ICMP flood attacks** (DDoS).
    

### **SNMP (Simple Network Management Protocol)**

- **Monitors network devices** (routers, switches).
    
- **Risk**: Default credentials (`public/private`) → **SNMP exploits**.

---

# **Additional Network Protocols**

---

## **1. Network Address Translation (NAT)**

### **Purpose**

- Allows **private IP devices** to communicate with the **public internet** using a **single public IP**.
    
- Conserves IPv4 addresses by reusing private IP ranges.
    

### **How NAT Works**

1. **Private IP Range** (LAN):
    
    - `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`
        
2. **Public IP** (WAN):
    
    - Assigned by ISP (e.g., `203.0.113.5`).
        
3. **Translation Process**:
    
    - Outgoing traffic: Router replaces **private source IP** with **public IP**.
        
    - Incoming traffic: Router maps **public IP** back to **private IP**.
        

### **Types of NAT**

|Type|Description|Use Case|
|---|---|---|
|**Static NAT**|1:1 mapping (private IP ↔ public IP).|Hosting a public web server internally.|
|**Dynamic NAT**|Pool of public IPs assigned dynamically.|Offices with multiple users.|
|**PAT (Port Address Translation)**|Multiple private IPs share **one public IP** using port numbers.|Home Wi-Fi routers.|

### **Security Implications**

- **Hides internal network structure** (security through obscurity).
    
- **Vulnerable to NAT Slipstreaming** (bypassing firewalls via HTTP).
    

---

## **2. Dynamic Host Configuration Protocol (DHCP)**

### **Purpose**

- Automatically assigns **IP addresses, subnet masks, gateways, and DNS servers** to devices.
    
- Uses **UDP ports 67 (server) & 68 (client)**.
    

### **How DHCP Works (DORA Process)**

1. **Discover** → Client broadcasts: _"Need an IP!"_
    
2. **Offer** → DHCP server responds with an available IP.
    
3. **Request** → Client accepts the offer.
    
4. **Acknowledge** → Server confirms and assigns the IP.
    


---

## **3. Address Resolution Protocol (ARP)**

### **Purpose**

- Maps **IP addresses** to **MAC addresses** (local network).
    
- Works at **Layer 2 (Data Link)**.
    

### **How ARP Works**

1. **ARP Request** (Broadcast): _"Who has 192.168.1.1?"_
    
2. **ARP Reply** (Unicast): _"192.168.1.1 is at 00:1A:2B:3C:4D:5E"_.
    

### **Security Risks & Mitigations**

|Risk|Description|Mitigation|
|---|---|---|
|**ARP Spoofing/Poisoning**|Fake ARP replies redirect traffic (MITM).|**Dynamic ARP Inspection (DAI)**.|
|**MAC Flooding**|Overflows switch’s MAC table.|**Port Security**, MAC limiting.|

---

## **4. Telnet (TCP Port 23)**

### **Purpose**

- **Unencrypted** remote CLI access (legacy).
    
- **Insecure** (all data sent in plaintext).
    

### **Security Risks**

- **Sniffing attacks** (passwords exposed).
    
- **Brute-force attacks** (weak authentication).
    

### **Modern Replacement: SSH (Secure Shell)**

- **Encrypted alternative** (TCP port 22).
    
- Uses **AES, RSA** for secure authentication.
    

---

## **5. Email Protocols**

### **A. POP3 (Post Office Protocol v3)**

- **Purpose**: Downloads emails to **one device** (deletes from server by default).
    
- **Ports**:
    
    - Unencrypted: **TCP 110**
        
    - Encrypted (SSL/TLS): **TCP 995**
        

### **B. IMAP (Internet Message Access Protocol)**

- **Purpose**: Syncs emails **across multiple devices** (stores on server).
    
- **Ports**:
    
    - Unencrypted: **TCP 143**
        
    - Encrypted (SSL/TLS): **TCP 993**
        

### **C. SMTP (Simple Mail Transfer Protocol)**

- **Purpose**: Sends emails (works with **MTA** like Postfix).
    
- **Ports**:
    
    - Unencrypted: **TCP 25** (often blocked due to spam)
        
    - Encrypted (TLS): **TCP 587** (modern standard)
        