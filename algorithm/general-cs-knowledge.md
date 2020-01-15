# General Computer Science Knowledge

## TCP/IP (Transmission Control Protocol and the Internet Protocol)
- TCP originated in the initial network implementation in which it complemented the IP so the entire suite is commonly referred to as TCP/IP
- The monolithic Transmission Control Program was later divided into a modular architecture consisting of the Transmission Control Protocol at the transport layer and the Internet Protocol at the internet layer
- At the transport layer, TCP handles all handshaking and transmission details and presents an abstraction of the network connection to the application typically through a network socket interface
- TCP detects problems that loses, duplicates, or out-of-order deliveries of IP packets and requests re-transmission of lost data, rearranges out-of-order data and even helps minimize network congestion to reduce the occurence of the other problems.
- If the data still remains undelivered, the source is notified of this failure
- TCP abstracts the application's communication from the underlying networking details
- Used in WWW, FTP, Secure Shell, P2P, streaming media, etc...
- TCP is optimized for accurate delivery rather than timely delivery and can incur relatively long delays.  Therefore, it is not particularly suitable for real-time applications such as VoIP
- TCP is a reliable stream delivery service which guarantees that all bytes received will be identical with bytes sent and in the correct order
- Positive acknowledgement with retransmission is used to guarantee reliability
- Timer is needed in case a package gets lost or corrupted
- While IP handles actual delivery of the data, TCP keeps track of segments
- Example
    1. An HTML file is sent from a web server
    2. The TCP software layer of that server divides the sequence of file octets into segments and forwards them individually to the IP software layer
    3. The Internet Layer encapsulates each TCP segment into an IP packet by adding a header that includes the destination IP address
    4. When the client program on the destination computer receives them, the TCP layer (Transport Layer) reassembles the individual segments and ensures they are correctly ordered and error-free as it streams them to an application
- TCP accepts data from a data stream, divides it into chunks, and adds a TCP header creating a TCP segment
- TCP segment is then encapsulated into an IP datagram, and exchanged with peers
- TCP header
    - Source port
    - Destination port
    - Sequence number
    - Acknowledgment number
    - Data offset
    - Reserved
    - Flags: NS, CWR, ECE, and more, which all add up to 9 bits
    - Window size
    - Checksum
    - Urgent pointer
    - Options
    - Padding
- TCP protocol operations may be divided into three phases
- State changes during the lifetime of a TCP connection
    - LISTEN (server): waiting for a connection request from any remote TCP and port
    - SYN-SENT (client): waiting for a matching connection request after having sent a connection request
    - SYN-RECEIVED (server): waiting for a confirming connection request acknowledgment after having both received and sent a connection request
    - ESTABLISHED (both): represents an open connection, data received can be delievered to the user.  The normal state for the data transfer phase of the connection
    - FIN-WAIT-1 (both): waiting for a connection termination request from the remote TCP, or an acknowledgment of the connection termination request previously sent
    - FIN-WAIT-2 (both): waiting for a connection termination request from the remote TCP
    - CLOSE-WAIT (both): waiting for a connection termination request from the local user
    - CLOSING (both): waiting for a connection termination request acknowledgment from the remote TCP
    - LAST-ACK (both): waiting for an acknowledgment ofthe connection termination request previously sent to the remote TCP
    - TIME-WAIT (either server or client): waiting for enough time to pass to be sure the remote TCP received the acknowledgment of its connection termination request
    - CLOSED (both): no connection state at all
- Establishing a connection
    - Three-way handshake
    - The server must first bind to and listen at a port to open it up for connections, which is called a passive open
    - Then a client may initiate an active open
    - Three-way handshake
        1. SYN: the active open is performed by the client sending a SYN to the server.  The client sets the segment's sequence number to a random value A
        2. SYN-ACK: in response, the server replies with a SYN-ACK.  The acknowledgment number is set to one more than the received sequence number i.e. A+1, and the sequence number that the server chooses for the packet is another random number, B
        3. ACK: the client sends an ACK back to the server.  The sequence number is set to the received acknowledgement value i.e. A+1, and the acknowledgement number is set to one more than the received sequence number i.e. B+1
- Terminating a connection
    - Four-way handshake
    - Each side of the connection terminating independently
    1. FIN from Initiator -> 2. ACK from Receiver
    3. FIN from Receiver -> 4. ACK from Initiator
    - A connection can be "half-open", in which case one side has terminated its end, but the other has not.
        - The opened side could send any data into the connection
- TCP uses an end-to-end flow control protocol to avoid having the sender send data too fast for the TCP receiver to receive and process it reliably
- Vulnerabilities
    - Denial of service: By using a spoofed IP address and repeatedly sending purposely assembled SYN packets, followed by many ACK packets, attackers can cause the server to consume large amounts of resources keeping track of the bogus connections
    - This is known as a SYN flood attack

## Load balancing

## Proxy

## UDP (User Datagram Protocol)
- UDP is one of the core members of the Internet Protocol (IP) suite
- With UDP, computer applications can send messages, in this case referred to as datagrams, to other hosts on an IP network
- UDP uses a simple connectionless communication model with a minimum of protocol mechanism
- It provides checksums for data integrity, and port numbers for addressing different functions at the source and destination of the datagram
    - A checksum is a small-sized datum derived from a block of digital data for  the purpose of detecting errors which may have been introduced during its transmission or storage
- No handshaking dialogues
    - Exposing the user's program to any unreliability of the underlying network
- No Guarantee of delivery, ordering, or duplicate protection
- UDP is suitable for purposes where error checking and correction are either not necessary or are performed in the application
- 