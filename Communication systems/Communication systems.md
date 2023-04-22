[wiki](https://en.wikipedia.org/wiki/Communications_system)

```toc
```
## Roles

**Information exchange with other research groups (interconnection)**
Via:
- e-mail
- FTP
- www
We use [[GAN]] and [[WAN]] that are under control of national telecom.

**Connection of computers intra-company**
Via [[LAN]]

**Data communication btwn experimental apparatus and laboratory computers**
Via: [[IEEE 488 BUS or GPIB BUS]]

![[Communication systems 2022-12-20 14.22.56.excalidraw]]

## Message encoding

![[Communication systems 2022-12-20 14.11.37.excalidraw]]
 Each symbol has a corresponding unique binary number. $2^n$ symbols can be encoded. (n is the number of bits)
 _example_: The ASCII code

## Components

### Message line
- Transmits the data in a directional manner (duplex (two way), half duplex (one way) same as simplex). 
- The data can be serial or parallel bit transmission. 

### Message broker
- Forwards the messages
- Selects addresses or message lines
- 
**Line switch**
Analogous to the telephone

**Package broker**
Analogous to letters

### Data Stations
The units that exchange messages with each other

### Structures
![[Pasted image 20221104140428.png]]

### Examples
- #### PC Internal BUS 
	- Form the expandability of PC's, external device connection
- #### Point to point
	- Modem connections (RS232, serial asynchronous transmission)
	- Centronics interface (8bit parallel) in printers
- #### USB, Firewire
	- Wider bit parallelism and faster buses
- #### FTP
- #### [[IEEE 488 BUS or GPIB BUS]]

## Protocols
Set of rules that define the temporal and logical sequence of data transmission (=convention). Implementable in hardware and software.
Multiple protocols can be combined to form a protocol stack, view: [[TCPIP protocol]]

## [[External Bus sytems]]

## [[LAN and WAN]]

## [[Networks]]
