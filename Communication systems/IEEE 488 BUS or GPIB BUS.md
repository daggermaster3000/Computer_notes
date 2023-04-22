```toc
```

## Intro
![[Pasted image 20221104141500.png]]
- Uses negative logic with standard transistor-transistor logic signals. (TTL)

## Communication

### Lines
Has 16 lines.
- 8 data lines (DIOX)
- 3 handshake lines (DAtaValid | NotReadyForData | NotDataACcepted)
- 5 control lines

### Logic
The negative TTL logic is as follows: 
- if DAV line $true$ $\rightarrow$ TTL signal is low
- if DAV line $false$ $\rightarrow$ TTL signal is high

### Handshake
![[Pasted image 20221220162314.png]]
```mermaid
graph TD
Transmitter --> DataBus
DataBus --> A{NRFD?}
A -->|1| DataBus
A -->|0| DAV=1
DAV=1 --> J{NDAC?}
J -->|1| DAV=1
J -->|0| DAV=0
DAV=0 --> R(Receiver)
R --> D(DAV?)
D -->|0| R
D -->|1| N(NFRD=1)
N --> readdata
readdata --> B(NDAC=0)
B --> DAV?
DAV? -->|1| B 
DAV? -->|0| NDAC=1
NDAC=1 --> Processdata
Processdata --> NFRD=0

```

[link](http://www.hit.bme.hu/~papay/edu/GPIB/tutor.htm)
 
![[Pasted image 20221104141500.png]]
![[Pasted image 20221104143140.png]]
GPIB Devices can be Talkers, Listeners, and/or Controllers. A **Talker** sends data messages to one or more **Listeners**, which receive the data. The **Controller** manages the flow of information on the GPIB by sending commands to all devices. A digital voltmeter, for example, is a Talker and is also a Listener.

The GPIB is like an ordinary computer bus, except that a computer has its circuit cards interconnected via a backplane - the GPIB has stand-alone devices interconnected by standard cables.

The role of the GPIB Controller is comparable to the role of a computer CPU, but a better analogy is to compare the Controller to the switching center of a city telephone system.

The switching center (Controller) monitors the communications network (GPIB). When the center (Controller) notices that a party (device) wants to make a call (send a data message), it connects the caller (Talker) to the receiver (Listener).

The Controller usually addresses (or enables) a Talker and a Listener before the Talker can send its message to the Listener. After the message is transmitted, the Controller may address other Talkers and Listeners.

Some GPIB configurations do not require a Controller. For example, a device that is always a Talker, called a talk-only device, is connected to one or more listen-only devices.

A Controller is necessary when the active or addressed Talker or Listener must be changed. The Controller function is usually handled by a computer.

A computer with the appropriate hardware and software could perform the roles of Talker/Listener and Controller.

- Handshake 
![[Pasted image 20221104142638.png]]
Three lines **asynchronously** control the transfer of message bytes between devices. The process is called a **3-wire interlocked handshake**. It guarantees that message bytes on the data lines are sent and received without transmission error.

-   NRFD (not ready for data) - Indicates when a device is ready or not ready to receive a message byte. The line is driven by all devices when receiving commands, by Listeners when receiving data messages, and by the Talker when enabling the HS488 protocol.
-   NDAC (not data accepted) - Indicates when a device has or has not accepted a message byte. The line is driven by all devices when receiving commands, and by Listeners when receiving data messages.
-   DAV (data valid) - Tells when the signals on the data lines are stable (valid) and can be accepted safely by devices. The Controller drives DAV when sending commands, and the Talker drives DAV when sending data messages.