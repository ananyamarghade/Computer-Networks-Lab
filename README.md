# Computer Networks Laboratory

A comprehensive, curriculum-aligned repository containing practical implementations, protocol analysis studies, and architectural documentation for the undergraduate Computer Networks Laboratory course (B.Tech Computer Science and Engineering).

This repository covers foundational networking hardware, socket programming using the POSIX Berkeley Sockets API in C (TCP and UDP), terminal-based DNS and ICMP diagnostics, packet inspection, flow control protocols, traffic shaping algorithms, and distributed routing algorithms.

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
│   ├── README.md                            # Theory, architecture & working principles
│   └── tcp_server.c                         # Clean TCP server socket code
│
├── Experiment-03-TCP-Client/
│   ├── README.md                            # Theory, connection logic & working principles
│   └── tcp_client.c                         # Clean TCP client socket code
│
├── Experiment-04-UDP-Server/
│   ├── README.md                            # Datagram socket architecture & working principles
│   └── udp_server.c                         # Clean UDP echo server code
│
├── Experiment-05-UDP-Client/
│   ├── README.md                            # Connectionless client mechanics & working principles
│   └── udp_client.c                         # Clean UDP interactive client code
│
├── Experiment-06-DNS-Commands/
│   └── README.md                            # Terminal diagnostic commands reference
│
├── Experiment-07-Wireshark-Analysis/
│   └── README.md                            # Deep packet inspection, DNS & HTTP/TLS analysis
│
├── Experiment-08-Sliding-Window/
│   ├── README.md                            # Flow control theory, pipeline math & algorithm
│   └── sliding_window.c                     # Sliding window (Go-Back-N) simulation code
│
├── Experiment-09-Traffic-Shaping/
│   ├── README.md                            # Leaky Bucket & Token Bucket theory and algorithms
│   ├── leaky_bucket.c                       # Clean Leaky Bucket implementation
│   └── token_bucket.c                       # Clean Token Bucket implementation
│
└── Experiment-10-Distance-Vector/
    ├── README.md                            # Bellman-Ford routing algorithm & convergence study
    └── distance_vector.c                    # Distance Vector routing table computation code
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
