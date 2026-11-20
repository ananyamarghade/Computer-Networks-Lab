# Experiment 05: UDP Client Socket Programming

## 1. Experiment Title
Implementation of a Connectionless UDP Client Using Datagram Sockets in C.

---

## 2. Aim
To design, implement, and evaluate an interactive UDP client in C using POSIX datagram sockets (`SOCK_DGRAM`). The client transmits user-defined text messages to the UDP server listening on `127.0.0.1:10004` using `sendto()`, receives the echoed payload via `recvfrom()`, and displays the response on the terminal.

---

## 3. Theory / Introduction
In UDP communication, the client does not establish a persistent virtual circuit with the server. Instead, it directly encapsulates each data payload into an independent datagram with the destination IP address and port number embedded in the transport header.

### 3.1 UDP Client Socket Lifecycle

```
        socket()           --> Create datagram socket (AF_INET, SOCK_DGRAM)
           |
     +-----> fgets()       --> Read interactive message string from user input
     |         |
     |      sendto()      --> Transmits datagram to target Server (127.0.0.1:10004)
     |         |
     |      recvfrom()    --> Waits for and receives echoed datagram
     |         |
     |      printf()      --> Displays echoed message on console
     |         |
     +---------+           --> Continues until user terminates
           |
         close()           --> Releases socket descriptor
```

### 3.2 Contrast: TCP Client vs. UDP Client

| Architectural Feature | TCP Client (Exp 03) | UDP Client (Exp 05) |
|---|---|---|
| **Connection Setup** | Three-way handshake (`connect()` required) | None (`connect()` is optional) |
| **Transmission Call** | `send()` / `write()` | `sendto()` with destination address |
| **Reception Call** | `read()` / `recv()` | `recvfrom()` with address capture |
| **Data Boundary** | Continuous byte stream (no boundaries) | Preserved message/datagram boundaries |
| **State Tracking** | Connection state maintained by kernel | Stateless; each datagram is independent |
| **Server Offline Error** | `connect()` returns `Connection Failed` | `sendto()` succeeds (packet dropped silently by OS/network) |

---

## 4. Objectives
1. Understand the operational mechanics of connectionless UDP client communication.
2. Implement message framing and socket transmission using `sendto()`.
3. Receive echoed server packets using `recvfrom()` without a prior connection establishment.
4. Observe the lack of connection state and immediate datagram transmission.

---

## 5. Required Software and Tools
- **Operating System:** Linux (Ubuntu 20.04/22.04/24.04), WSL (Windows Subsystem for Linux), or any POSIX-compliant UNIX environment.
- **Compiler:** GCC (GNU Compiler Collection).
- **Text Editor / IDE:** Gedit, Nano, Vim, or Visual Studio Code.
- **Terminal:** Bash / GNOME Terminal / Windows Terminal.

---

## 6. Algorithm / Working Principle
1. Start the program.
2. Instantiate a UDP datagram socket using `socket(AF_INET, SOCK_DGRAM, 0)`.
3. If socket creation returns a negative value, display an error and terminate.
4. Set up the destination server address structure (`sockaddr_in server_addr`):
   - Set `sin_family = AF_INET`.
   - Set `sin_port = htons(PORT)` (`10004`).
   - Convert string IP address `"127.0.0.1"` into numeric format using `inet_addr()`.
5. Enter a loop:
   - Read input line into `buffer` using `fgets()`.
   - Send the message datagram to the server using `sendto()`.
   - Clear the reception buffer with `memset()`.
   - Receive the echoed response datagram from the server using `recvfrom()`.
   - Null-terminate the received buffer and print response.
6. Close the socket using `close()`.
7. End the program.

---

## 7. Result / Conclusion
An interactive UDP client was successfully implemented in C using POSIX datagram sockets. The experiment demonstrated connectionless socket creation, packet encapsulation, datagram transmission using `sendto()`, and response reception using `recvfrom()`.

---

## 8. Important Viva Questions with Answers

### Q1: What happens if a UDP client sends data to a port where no server is running?
**Answer:** The `sendto()` system call will still succeed locally and return the number of bytes written to the kernel buffer. However, the destination host will typically respond with an ICMP "Port Unreachable" message. If the UDP socket is unconnected, this ICMP error is usually not delivered to the application.

### Q2: Can `connect()` be called on a UDP socket?
**Answer:** Yes. Calling `connect()` on a UDP socket does not perform a network handshake; instead, it associates the socket descriptor with a specific remote IP and port in the local kernel. This allows the program to use `send()` and `recv()` instead of `sendto()` and `recvfrom()`, and filters incoming packets to only those from the connected peer.

### Q3: Why is UDP preferred over TCP for real-time video streaming or online gaming?
**Answer:** Real-time applications prioritize low latency over 100% reliability. TCP's retransmission delays, head-of-line blocking, and congestion back-off mechanisms cause unacceptable jitter. In contrast, UDP sends data immediately without retransmissions, allowing frames with minor loss to be skipped in favor of real-time continuity.

### Q4: Does UDP provide flow control or congestion control?
**Answer:** No. UDP does not implement flow control (sliding window) or congestion control (AIMD/slow start). If a UDP sender transmits faster than the receiver can process or faster than intermediate routers can forward, buffers overflow and packets are dropped.

### Q5: What is the size of the UDP header, and what fields does it contain?
**Answer:** The UDP header is fixed at **8 bytes** (64 bits) and contains four 16-bit fields:
1. **Source Port** (16 bits)
2. **Destination Port** (16 bits)
3. **Length** (16 bits, header + payload length)
4. **Checksum** (16 bits, error detection)
