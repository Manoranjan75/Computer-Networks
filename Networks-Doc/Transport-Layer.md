# Transport Layer: Complete Overview  

The **Transport Layer (Layer 4 of the OSI Model)** ensures reliable process-to-process delivery of data.  
While the Network Layer handles host-to-host delivery, the Transport Layer makes sure that data reaches the **right process** within the right host.  

---

## 1. Core Concepts and Functions  
- Ensures **end-to-end communication** between processes.  
- Provides **segmentation and reassembly** of data.  
- Handles **error detection, flow control, and congestion control**.  
- Uses **port numbers** to identify specific processes.  

---

## 2. Multiplexing and Demultiplexing  
- **At Sender Side:** Multiple processes send data → multiplexed into a single stream.  
- **At Receiver Side:** Stream is demultiplexed → delivered to the correct process.  
- **Based on Port Numbers:**  
  - Error checking → Header removal → Delivered to right process.  

---

## 3. Segmentation and Reassembly  
- **Segmentation (Sender):** Service Data Unit (SDU) divided into Protocol Data Units (PDUs).  
- **Reassembly (Receiver):** PDUs combined back into SDU.  
- Ensures that large messages are broken into manageable segments.  

---

## 4. Port Numbers  
- **16-bit addresses (0–65,535)** used to identify processes.  
- **Destination Port:** Needed for message delivery.  
- **Source Port:** Needed for reply messages.  
- **Well-Known Ports (0–1023):** Reserved for standard services (e.g., HTTP = 80, SMTP = 25).  
- **Temporary Ports (dynamic):** Used by clients during communication.  

---

## 5. IP Addresses vs Port Numbers  
- **IP Address:** Identifies the host (machine).  
- **Port Number:** Identifies the process on that host.  
- **Together:** Provide the complete data destination.  

---

## 6. Service Types  

### A. Connection-Oriented Services  
- Establishes a **connection** before data transfer.  
- Uses **sequence numbers** to order segments.  
- **Phases:**  
  1. Connection Setup  
  2. Data Transfer  
  3. Connection Release  
- **Examples:** TCP, SCTP, ATM  

### B. Connectionless Services  
- Each segment is treated independently.  
- **No setup, no guarantee of order or delivery.**  
- **Example:** UDP  

---

## 7. Transport Layer Protocols  

### A. User Datagram Protocol (UDP)  
- **Type:** Connectionless, unreliable.  
- **Use Case:** Real-time applications (VoIP, DNS).  
- **Efficiency:** Low overhead, faster than TCP.  

**UDP Header (8 bytes):**  
- Source Port (16 bits)  
- Destination Port (16 bits)  
- Length (16 bits)  
- Checksum (16 bits)  

**Operations:**  
- Independent datagrams  
- No flow/error control  
- Encapsulation into IP datagrams  
- Simple queuing mechanism  

---

### B. Transmission Control Protocol (TCP)  
- **Type:** Connection-oriented, reliable.  
- **Characteristics:** Stream-oriented, ensures error-free, ordered delivery.  

**TCP Features:**  
- **Flow Control:** Prevents overflow using window mechanism.  
- **Error Control:** Checksum, acknowledgment, retransmission.  
- **Congestion Control:** Adjusts to network load.  
- **Buffering:** Temporary storage for smooth transmission.  

**TCP Segment Structure:**  
- Ports (source/destination)  
- Sequence & acknowledgment numbers  
- Flags (SYN, ACK, FIN, etc.)  
- Window size, checksum  

**TCP Connection Management:**  
- **Three-Way Handshake:**  
  1. SYN → 2. SYN+ACK → 3. ACK  
- **Termination:**  
  FIN → FIN+ACK → ACK  

---

### C. Stream Control Transmission Protocol (SCTP)  
- **Type:** Reliable, message-oriented.  
- **Purpose:** Designed for advanced internet apps.  
- **Key Features:**  
  - Supports **multiple streams**  
  - **Message-oriented** (not byte stream)  
  - **Separate chunks** for data & control  
  - **Verification tag** as identifier  

**SCTP Connection Management:**  
- **Four-Way Handshake:** INIT → INIT ACK → COOKIE ECHO → COOKIE ACK  
- **Termination:** SHUTDOWN → SHUTDOWN ACK → SHUTDOWN COMPLETE  

---

## 8. SCTP vs TCP  

| Feature              | TCP                         | SCTP                        |  
|----------------------|-----------------------------|-----------------------------|  
| Data Orientation     | Byte-stream                 | Message-oriented            |  
| Streams              | Single stream               | Multiple streams            |  
| Control & Data       | Same segment                | Separate chunks             |  
| Connection Setup     | 3-way handshake             | 4-way handshake             |  
| Identifier           | Connection state variables  | Verification tag            |  

---
