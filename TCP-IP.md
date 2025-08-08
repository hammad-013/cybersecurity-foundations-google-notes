## **TCP/IP Model with Practical Examples**

### Imagine: You're using your browser to visit `https://example.com`

---

### **1. Application Layer**

**Purpose:** Deals with the actual user applications — browsers, email apps, etc.

**Example:**

- You open **Google Chrome** and type `https://example.com`.
- The browser uses the **HTTPS protocol** to request the webpage.

**Port used:** `443` (Secure web traffic)

**Other Examples:**

- Sending email via Gmail → uses **SMTP (Port 25)**
- Downloading a file via FTP → uses **FTP (Port 20)**    

---

### **2. Transport Layer**

**Purpose:** Manages communication between your device and the web server.

**Example:**

- Your browser uses **TCP** to create a **connection** with the web server at `example.com`.
    
- TCP ensures:
    - All website data (images, text, code) is split into **packets**.
    - The packets are numbered and sent in order.
    - If a packet is lost, TCP **resends** it.     

Think of TCP like sending a **registered mail** where delivery is guaranteed.

---

### **3. Internet Layer**

**Purpose:** Ensures the packets reach the correct destination IP address.

**Example:**

- Your system figures out that `example.com` is hosted at IP `93.184.216.34` using DNS.

- Then IP protocol routes the packets:
    - From your IP (e.g., `192.168.0.10`)        
    - To the destination IP (`93.184.216.34`)
-  ICMP is also used in this layer.

- Routers on the internet use IP addresses to **forward** packets.    

Think of IP like a **home address** on an envelope.

---

### **4. Network Access Layer (Link Layer)**

**Purpose:** Deals with physical data transmission over wires or wireless.

**Example:**

- Your laptop sends packets over **Wi-Fi** or **Ethernet cable** to the nearest router.
- The router then sends it to the ISP and further across the internet.

Think of this as the **delivery truck** or the **postman** physically moving your letters.

---

## Full Practical Flow:

**User opens browser** → `https://example.com`

| Layer                | Protocol Used  | Real-World Action                                                  |
| -------------------- | -------------- | ------------------------------------------------------------------ |
| Application Layer    | HTTPS          | Browser requests a secure webpage (Port 443)                       |
| Transport Layer      | TCP            | Ensures all webpage packets arrive completely and in order         |
| Internet Layer       | IP             | Routes data from your device’s IP to the web server’s IP           |
| Network Access Layer | Ethernet/Wi-Fi | Sends packets over physical network to ISP and across the internet |

---
### Memory Trick:

> **A-T-I-N** → "All Things In Network"

| A           | T         | I        | N              |
| ----------- | --------- | -------- | -------------- |
| Application | Transport | Internet | Network Access |
![image](tcpip.png)