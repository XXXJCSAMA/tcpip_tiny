# tcpip_tiny
Implement ARP/IP(including fragmentation and reassembly)/UDP/TCP protocol,
provide BSD socket programming interface, 
support to run multiple application clients and servers at the same time.
At present, it has been ported to the x86 operating system and ARM development board written by himself.
Protocol stack characteristics
Platform support
Supports development and learning on Windows, Linux, and Mac platforms
The C language uses the C99 standard and does not rely on a specific compiler
The code is highly portable and can be easily ported to x86 and embedded platforms such as ARM
Only the operating system needs to provide basic semaphore, mutex and time acquisition interface to support hardware
It does not limit the specific network interface type, and supports other interface devices other than Ethernet
Support to add multiple network interfaces (nics), IP packets will automatically be sent to the correct interface according to the routing table
Support loopback interface, to achieve the local packet self-collection function features
Standard Socket interface:
Interfaces: socket, bind, connnect, close
Interfaces: sendto, recvfrom, send, recv, read, write, setsockopt
Concrete type
SOCK_RAW: Allows applications to send and receive IP packets
Sock_dgram-based: Allows applications to send and receive UDP packets
Sock_stream-based (under development) : Allows applications to send and receive UDP packets
multithreading
Supports multi-threading operations on the same socket interface, that is, allows different threads to read and write at the same time
Supports the creation of any number of applications at the same time, whether client or server
Data packet
Organize packets into multiple blocks of links to improve memory utilization efficiency
Ethernet protocol: Supports Ethernet packet sending and receiving and packet processing
Address resolution Protocol (ARP)
Complete support for ARP query and response processes
Supports the sending of gratuitous ARP packets
Use a configurable size of ARP buffer
