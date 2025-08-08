## **What is a Firewall?**

A firewall is a **network security device** that monitors and controls incoming/outgoing traffic based on **predefined security rules**. It acts as a barrier between **trusted internal networks** and **untrusted external networks** (like the Internet).

---

## **How Firewalls Work**

1. **Inspects traffic** (source/destination IP, port, protocol).
    
2. **Compares traffic against rules** (allow/block/drop).
    
3. **Logs activity** for security analysis.
    
4. **Can be hardware or software-based**.
   
## **Stateless Firewalls (Packet-Filtering Firewalls)**

### **How They Work**

- **Examines each packet in isolation** (no memory of past packets).
    
- **Fast but less secure** (easier to bypass).
    
- **Uses ACLs (Access Control Lists)** to filter traffic.
    

### **Example Rule**

```
ALLOW TCP 192.168.1.10 → 8.8.8.8 PORT 80 (HTTP)
DENY ALL OTHER TRAFFIC
```

### **Pros & Cons**

| **Pros**            | **Cons**                          |
| ------------------- | --------------------------------- |
| Fast (low latency)  | No session tracking               |
| Simple to configure | Vulnerable to spoofing            |
| Low resource usage  | Can’t detect multi-packet attacks |
## **Stateful Firewalls**

### **How They Work**

- **Tracks connection state** (remembers active sessions).
    
- **Only allows return traffic for established connections**.
    
- **More secure but slightly slower**.
    

### **Example Workflow**

1. **Client** (`192.168.1.10`) sends `SYN` to **Server** (`8.8.8.8:80`).
    
2. **Firewall logs this as a new connection** in its **state table**.
    
3. When **server responds** (`SYN-ACK`), firewall **allows it** (matches state table).
    
4. **Blocks unsolicited inbound traffic**.
    

### **Pros & Cons**

| **Pros**                     | **Cons**                   |
| ---------------------------- | -------------------------- |
| Stops spoofing & scanning    | Higher CPU/memory usage    |
| Prevents unauthorized access | More complex configuration |
| Logs connection states       | Slight latency increase    |