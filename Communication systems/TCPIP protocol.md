> How does the data get to its destination? The TCP/IP protocol finds the path in the network of computers

```toc
```

## Addressing
IP addresses allow unique identification of the target computer

### IPv4
The address consists of 4 bytes (0...255) that are divided into the **network** address and the **host** address
(the division depends on the class of the network) (UZH is class B)
![[Pasted image 20221220180205.png]]
Max $2^{32}$ addresses

### IPv6
IPv4 was not thicc enough for the growing number of computers, enter IPv6.
The addresses are based on 8 blocks of 16-bits, divided into 16 bit prefix and 64 bit interface identifier.
![[Pasted image 20221220180325.png]]
The prefix is divided into **network** address and **host** address
The interface id is usually the MAC address.
The suffix determines the size of the network(number of bits of the network address)
Max $2^{128}$ addresses

## Routing
**Gateways** or **routers** transmit the data to the correct network

### Routing tables
Each host (=computer) and each gateway has a routing table. It assigns a gateway to the network part of an IP address. 
![[Pasted image 20221220183244.png]]
They are generated by hand (static routing table). The gateway has the job of forwarding what it received from the host (the host knows nothing of the outside world) or by routing protocols that generate them dynamically.

### Routing architecture

...

## Multiplexing
Protocols and port numbers direct the data to the correct process/user within the computer. When the data ascends layers to the application layer the process that uses it is determined by multiplexing (based on the port number).
![[Pasted image 20221220183816.png]]
## DNS
Domain name service is an application layer protocol that converts IP addresses to names. It's a global database with a local cache.
The namespaces are delegated hierachicaly. Each domain has a server that is initialized with a cache of 13 root name servers. Domains are applied for at the NIC
![[Pasted image 20221220184122.png]]