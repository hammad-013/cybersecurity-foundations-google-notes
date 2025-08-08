How data is transferred when you type [www.example.com](http://www.example.com), mapped to the 7-layer OSI model?

## 1. Application Layer (OSI Layer 7)

**What happens:**

- Your browser (HTTP client) creates an HTTP GET request
- DNS resolution occurs (converting [www.example.com](http://www.example.com) to an IP address)

**Example Data:**
```

GET / HTTP/1.1
Host: www.example.com
```

**Encapsulation:**

- Raw application data is created
- Passed to Presentation Layer

## 2. Presentation Layer (OSI Layer 6)

**What happens:**

- Data formatting (character encoding, compression if used)
- Encryption if using HTTPS (TLS/SSL)
- Conversion between application and network formats

## 3. Session Layer (OSI Layer 5)

**What happens:**

- Establishes, manages, and terminates the connection session
- For HTTP, this is typically handled by TCP at layer 4

## 4. Transport Layer (OSI Layer 4)

**What happens:**

- HTTP message is wrapped in a TCP segment
- Adds TCP header with:
    - Source Port (random ephemeral port, e.g., 49152)
    - Destination Port (80 for HTTP, 443 for HTTPS)
    - Sequence numbers, acknowledgment numbers, window size, flags (SYN, ACK, etc.)

**Encapsulation Result:**  
`[TCP Header][HTTP Data]`

**Purpose:**

- Ensures reliable end-to-end communication
- Flow control and error recovery

## 5. Network Layer (OSI Layer 3)

**What happens:**

- TCP segment is wrapped in an IP packet
- Adds IP header with:
    - Source IP (your device's IP)
    - Destination IP (server's IP, e.g., 93.184.216.34)
    - Protocol type (TCP)
    - TTL (Time To Live)

**Encapsulation Result:**  
`[IP Header][TCP Header][HTTP Data]`

**Purpose:**

- Logical addressing and routing
- Fragmentation if needed

## 6. Data Link Layer (OSI Layer 2)

**What happens:**

- IP packet is wrapped in a frame (Ethernet, Wi-Fi, etc.)
- Adds frame header with:
    - Source MAC address (your NIC)
    - Destination MAC address (next hop, usually your router)
    - Frame check sequence (FCS) for error detection

**Encapsulation Result:**  
`[Frame Header][IP Header][TCP Header][HTTP Data][Frame Trailer]`

**Purpose:**

- Reliable node-to-node delivery
- MAC addressing
- Error detection (not correction)

## 7. Physical Layer (OSI Layer 1)

**What happens:**

- Frame is converted to physical signals:
    - Electrical signals (Ethernet)
    - Radio waves (Wi-Fi)
    - Light pulses (fiber)
- Bit-level transmission

**Transmission:**

- Signals travel through cables, switches, routers
- Each device processes the appropriate layers:
    - Switches work at Layer 2
    - Routers work at Layer 3
    - Your computer processes all layers        

## At the Server (Decapsulation):

1. Physical layer converts signals to bits
2. Data Link layer:
    - Checks frame integrity (FCS)
    - Strips frame headers/trailers
3. Network layer:
    - Verifies IP address
    - Strips IP header
4. Transport layer:
    - Verifies TCP information
    - Reassembles segments if fragmented
    - Strips TCP header
5. Session/Presentation layers (if applicable)
6. Application layer receives the HTTP request