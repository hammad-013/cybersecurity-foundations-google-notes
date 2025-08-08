## **1. What is a Proxy?**

A **proxy server** acts as an **intermediary** between a client (you) and the internet.

### **How It Works:**

1. Your request → Proxy server → Internet
    
2. Website sees the **proxy's IP** (not yours)
    
3. Response → Proxy → You
    

### **Key Features:**

|Feature|Description|
|---|---|
|**Anonymity**|Hides your real IP address|
|**Content Filtering**|Blocks malicious/restricted sites|
|**Caching**|Stores frequent requests for faster access|
|**Logging**|Can track user activity|

### **Use Cases:**

- **Privacy protection** (hiding your IP)
    
- **Bypassing geo-blocks** (accessing region-locked content)
    
- **Corporate web filtering** (blocking social media at work)
    

### **Types of Proxies:**

- **Forward Proxy** (Standard proxy for clients)
    
- **Transparent Proxy** (No anonymity; used for caching/filtering)
    
- **SOCKS Proxy** (Handles any traffic type, e.g., torrents)
    

---

## **2. What is a Reverse Proxy?**

A **reverse proxy** sits in front of **servers** (not clients), handling requests on their behalf.

### **How It Works:**

1. User request → Reverse proxy → Backend server
    
2. Backend response → Reverse proxy → User
    

### **Key Features:**

|Feature|Description|
|---|---|
|**Load Balancing**|Distributes traffic across multiple servers|
|**SSL Termination**|Handles HTTPS encryption/decryption|
|**DDoS Protection**|Filters malicious traffic before it hits servers|
|**Caching**|Speeds up static content delivery|

### **Use Cases:**

- **Protecting web servers** (hiding origin server IPs)
    
- **Improving performance** (caching, compression)
    
- **Simplifying deployments** (single entry point for multiple apps)
    

### **Popular Reverse Proxy Tools:**

- **Nginx**
    
- **Apache HTTP Server (mod_proxy)**
    
- **Cloudflare** (CDN + reverse proxy)