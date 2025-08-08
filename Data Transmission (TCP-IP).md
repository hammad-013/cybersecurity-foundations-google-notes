# Scenario:

You open a browser and type www.example.com → Press Enter.
📦 TCP/IP Model Overview:

## The TCP/IP model has 4 layers:

    Application Layer
    Transport Layer
    Internet Layer
    Network Access (Link + Physical) Layer

## 🔁 Data Transformation Through the Layers
## 1. Application Layer

What happens:

Your browser sends an HTTP GET request to www.example.com.

Example Data:

```
GET / HTTP/1.1
Host: www.example.com
```


Encapsulation Result:
    This is the raw message (application data).
    Passed to the Transport Layer.
## 2. Transport Layer (TCP)

What happens:

 The HTTP request is wrapped into a TCP segment.
   Adds a TCP header with:
    Source Port (e.g., 49152)
    Destination Port (e.g., 80 for HTTP or 443 for HTTPS)
	Sequence number, flags, etc.

Encapsulation Result:

`[TCP Header][HTTP Request]`

Purpose:

    Ensures reliable transmission.
    If data is lost, TCP requests retransmission.

## 3. Internet Layer (IP)

What happens:

    TCP segment is wrapped in an IP packet.
    Adds an IP header with:
        Source IP (your device)
        Destination IP (web server)

Encapsulation Result:

`[IP Header][TCP Header][HTTP Request]`

Purpose:

    Defines where the packet is going (routing).
    Each router reads only the IP header to forward the packet.

## 4. Network Access Layer (Link Layer + Physical Layer)
### A. Link Layer (e.g., Ethernet)

What happens:

    The IP packet is wrapped in a frame.
    Adds a Frame Header:
        MAC address of your device
        MAC address of the next hop (router/gateway)

Encapsulation Result:

`[Ethernet Header][IP Header][TCP Header][HTTP Request][Ethernet Trailer]`

### B. Physical Layer

What happens:

    The final frame is converted into electrical signals, radio waves, or light pulses, depending on the medium:

        Wired (Ethernet): electrical signals
        Wi-Fi: radio waves
        Fiber: light pulses

## 📤 Transmission:

These physical signals travel through:

    Cables
    Switches
    Routers
    ...until they reach the destination server.

## 📥 At the Server:

The entire process is reversed (decapsulation):

   - Physical signals are converted to binary.
   - Ethernet frame is read and stripped.
   - IP packet is read, used for routing.
  - TCP segment is checked, verified.
   - HTTP request is extracted and sent to the web server software (e.g., Apache, Nginx).