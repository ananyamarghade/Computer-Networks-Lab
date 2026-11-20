# Computer Networks Laboratory

A comprehensive, curriculum-aligned repository containing practical implementations, protocol analysis studies, and packet capture labs for the undergraduate Computer Networks Laboratory course (B.Tech Computer Science and Engineering).

This repository covers foundational networking hardware, socket programming using the POSIX Berkeley Sockets API in C (TCP and UDP), terminal-based DNS and ICMP diagnostics, deep packet inspection using Wireshark, flow control protocols, traffic shaping algorithms, and distributed routing algorithms.

---

## Course Information

- **Course Title:** Computer Networks Laboratory
- **Author:** Ananya Marghade
- **GitHub Repository:** [ananyamarghade/Computer-Networks-Lab](https://github.com/ananyamarghade/Computer-Networks-Lab)
- **Primary Language:** C (Standard C99 / POSIX Sockets)
- **Analysis Tools:** Wireshark, Command-Line Utilities (`nslookup`, `ping`, `ipconfig`, `tracert`)

---

## Experiment Index

| No. | Experiment Title | Category | Implementation / Tools | Description |
|---|---|---|---|---|
| **01** | [Basic Networking Elements and Devices](Experiment-01-Basic-Networking/README.md) | Network Architecture | Theory, Architectural Study | Study of Hub, Switch, Router, Bridge, Repeater, Gateway, Modem, NIC, and collision/broadcast domains. |
| **02** | [TCP Server Socket Programming](Experiment-02-TCP-Server/README.md) | Socket Programming | C (POSIX Sockets), GCC | Connection-oriented TCP server using `socket`, `bind`, `listen`, `accept`, `read`, and `send`. |
| **03** | [TCP Client Socket Programming](Experiment-03-TCP-Client/README.md) | Socket Programming | C (POSIX Sockets), GCC | TCP client connecting to server on `127.0.0.1:8080`, performing 3-way handshake and data exchange. |
| **04** | [UDP Server Socket Programming](Experiment-04-UDP-Server/README.md) | Socket Programming | C (POSIX Sockets), GCC | Connectionless UDP Echo Server using datagram sockets (`SOCK_DGRAM`) on port `10004`. |
| **05** | [UDP Client Socket Programming](Experiment-05-UDP-Client/README.md) | Socket Programming | C (POSIX Sockets), GCC | Interactive UDP client sending messages and receiving echoed datagrams via `sendto` and `recvfrom`. |
| **06** | [DNS Commands Using Terminal](Experiment-06-DNS-Commands/README.md) | Network Diagnostics | Terminal (`nslookup`, `ping`, `ipconfig`, `tracert`) | Practical demonstration of forward/reverse DNS lookups, cache inspection, and connectivity testing. |
| **07** | [DNS and HTTPS Packet Analysis Using Wireshark](Experiment-07-Wireshark-Analysis/README.md) | Packet Inspection | Wireshark, Npcap | Packet dissection of DNS queries/responses, comparison of plaintext HTTP vs encrypted HTTPS/TLS. |
| **08** | [Sliding Window Protocol](Experiment-08-Sliding-Window/README.md) | Flow Control | C Simulation, GCC | Simulation of Go-Back-N sliding window flow control with sender window, cumulative ACKs, and retransmission. |
| **09** | [Traffic Shaping Algorithms](Experiment-09-Traffic-Shaping/README.md) | Congestion Control | C Implementation, GCC | Implementation and comparative analysis of Leaky Bucket and Token Bucket traffic shaping algorithms. |
| **10** | [Distance Vector Routing Algorithm](Experiment-10-Distance-Vector/README.md) | Routing Algorithms | C Implementation, GCC | Distributed Bellman-Ford shortest-path routing algorithm with dynamic routing table updates and convergence. |

---

## Technologies and Tools Used

- **Programming Language:** C (GCC 13.x+, Standard C99/C11)
- **APIs:** POSIX Sockets (`<sys/socket.h>`, `<netinet/in.h>`, `<arpa/inet.h>`, `<unistd.h>`)
- **Packet Analysis:** Wireshark Network Protocol Analyzer (v4.x)
- **Operating Environments:** Linux (Ubuntu 22.04 / 24.04 LTS), Windows Subsystem for Linux (WSL), Windows Command Prompt / PowerShell
- **Version Control:** Git, GitHub

---

## Repository Structure

```text
Computer-Networks-Lab/
│
├── README.md                                # Root repository documentation
│
├── Experiment-01-Basic-Networking/
│   └── README.md                            # Networking devices, architecture & comparison
│
├── Experiment-02-TCP-Server/
│   ├── README.md                            # Comprehensive theory, guide & viva questions
│   ├── tcp_server.c                         # Clean TCP server socket code
│   └── screenshots/                         # Practical execution reference screenshots
│
├── Experiment-03-TCP-Client/
│   ├── README.md                            # TCP client guide, connection logic & viva questions
│   ├── tcp_client.c                         # Clean TCP client socket code
│   └── screenshots/                         # Practical execution reference screenshots
│
├── Experiment-04-UDP-Server/
│   ├── README.md                            # Datagram socket architecture & viva questions
│   ├── udp_server.c                         # Clean UDP echo server code
│   └── screenshots/                         # Practical execution reference screenshots
│
├── Experiment-05-UDP-Client/
│   ├── README.md                            # Connectionless client mechanics & viva questions
│   ├── udp_client.c                         # Clean UDP interactive client code
│   └── screenshots/                         # Practical execution reference screenshots
│
├── Experiment-06-DNS-Commands/
│   ├── README.md                            # Terminal diagnostic commands & output analysis
│   └── screenshots/                         # Command prompt execution screenshots
│
├── Experiment-07-Wireshark-Analysis/
│   ├── README.md                            # Deep packet inspection, DNS & HTTP/TLS analysis
│   └── screenshots/                         # Wireshark trace & packet dissection screenshots
│
├── Experiment-08-Sliding-Window/
│   ├── README.md                            # Flow control theory, pipeline math & viva questions
│   ├── sliding_window.c                     # Sliding window (Go-Back-N) simulation code
│   └── screenshots/                         # Execution output screenshots
│
├── Experiment-09-Traffic-Shaping/
│   ├── README.md                            # Leaky Bucket & Token Bucket theory and comparison
│   ├── leaky_bucket.c                       # Clean Leaky Bucket implementation
│   ├── token_bucket.c                       # Clean Token Bucket implementation
│   └── screenshots/                         # Execution output screenshots
│
└── Experiment-10-Distance-Vector/
    ├── README.md                            # Bellman-Ford routing algorithm & convergence study
    ├── distance_vector.c                    # Distance Vector routing table computation code
    └── screenshots/                         # Converged routing table screenshots
```

---

## Compilation and Execution Guide

### 1. TCP Server & Client (Experiments 02 & 03)
Open two separate terminal windows:
```bash
# Terminal 1 - Start Server:
cd Experiment-02-TCP-Server
gcc tcp_server.c -o server
./server

# Terminal 2 - Start Client:
cd Experiment-03-TCP-Client
gcc tcp_client.c -o client
./client
```

### 2. UDP Server & Client (Experiments 04 & 05)
Open two separate terminal windows:
```bash
# Terminal 1 - Start UDP Server:
cd Experiment-04-UDP-Server
gcc udp_server.c -o server
./server

# Terminal 2 - Start UDP Client:
cd Experiment-05-UDP-Client
gcc udp_client.c -o client
./client
```

### 3. Sliding Window Protocol (Experiment 08)
```bash
cd Experiment-08-Sliding-Window
gcc sliding_window.c -o sliding_window
./sliding_window
```

### 4. Traffic Shaping Algorithms (Experiment 09)
```bash
cd Experiment-09-Traffic-Shaping

# Leaky Bucket:
gcc leaky_bucket.c -o leaky_bucket
./leaky_bucket

# Token Bucket:
gcc token_bucket.c -o token_bucket
./token_bucket
```

### 5. Distance Vector Routing Algorithm (Experiment 10)
```bash
cd Experiment-10-Distance-Vector
gcc distance_vector.c -o distance_vector
./distance_vector
```

---

## Key Learning Outcomes

1. **Layer Encapsulation:** Mastered how application payloads traverse transport (TCP/UDP), network (IPv4), and data link (Ethernet II) layers.
2. **Socket Programming:** Gained practical proficiency in developing distributed client-server applications using connection-oriented and connectionless paradigms.
3. **Network Diagnostics:** Developed hands-on experience using terminal utilities (`nslookup`, `ping`, `ipconfig`, `tracert`) to diagnose connectivity and DNS configuration issues.
4. **Packet Dissection:** Acquired practical packet sniffing skills using Wireshark to inspect protocol headers, verify transaction handshakes, and identify unencrypted traffic vulnerabilities.
5. **Protocol Engineering:** Understood algorithmic principles governing reliable flow control (Sliding Window), congestion management (Leaky/Token Bucket), and distributed routing table convergence (Bellman-Ford Distance Vector).

---

## Author

- **Name:** Ananya Marghade
- **Profile:** [github.com/ananyamarghade](https://github.com/ananyamarghade)
- **Repository:** [Computer-Networks-Lab](https://github.com/ananyamarghade/Computer-Networks-Lab)
