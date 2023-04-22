Local and wide area network
![[Pasted image 20221111135420.png]]


## OSI model
The open systems Interconnections model defines a hierachical architecture for the exchange of information. The connection layers are implemented in a protocol stack, with the lowest layer is the most close to the process (less abstraction). 

There are 3 main layers:
- application layer
- transport layer 
- network layer
They are further divided into 7 layers. 

Communication between (within a node) (vertically) these layers is done via API's
Communication between different nodes (but same layer) (horizontal) is done with P2P protocols.

![[LAN and WAN 2022-12-20 17.07.12.excalidraw]]

**Overview of the model**
![[LAN and WAN 2022-12-20 17.21.17.excalidraw]]

<table class="wikitable" style="margin: 1em auto 1em auto;">
<caption>OSI model
</caption>
<tbody><tr>
<th colspan="3">Layer
</th>
<th><a href="/wiki/Protocol_data_unit" title="Protocol data unit">Protocol data unit</a> (PDU)
</th>
<th>Function
</th></tr>
<tr>
<th rowspan="4">Host<br>layers
</th>
<td style="background:#d8ec9b;">7
</td>
<td style="background:#d8ec9b;"><a href="/wiki/Application_layer" title="Application layer">Application</a>
</td>
<td style="background:#d8ec9c;" rowspan="3"><a href="/wiki/Data_(computing)" class="mw-redirect" title="Data (computing)">Data</a>
</td>
<td style="background:#d8ec9c;">High-level protocols such as for resource sharing or remote file access, e.g. <a href="/wiki/Hypertext_Transfer_Protocol" title="Hypertext Transfer Protocol">HTTP</a>.
</td></tr>
<tr>
<td style="background:#d8ec9b;">6
</td>
<td style="background:#d8ec9b;"><a href="/wiki/Presentation_layer" title="Presentation layer">Presentation</a>
</td>
<td style="background:#d8ec9b;">Translation of data between a networking service and an application; including <a href="/wiki/Character_encoding" title="Character encoding">character encoding</a>, <a href="/wiki/Data_compression" title="Data compression">data compression</a> and <a href="/wiki/Encryption" title="Encryption">encryption/decryption</a>
</td></tr>
<tr>
<td style="background:#d8ec9b;">5
</td>
<td style="background:#d8ec9b;"><a href="/wiki/Session_layer" title="Session layer">Session</a>
</td>
<td style="background:#d8ec9b;">Managing communication <a href="/wiki/Session_(computer_science)" title="Session (computer science)">sessions</a>, i.e., continuous exchange of information in the form of multiple back-and-forth transmissions between two nodes
</td></tr>
<tr>
<td style="background:#e7ed9c;">4
</td>
<td style="background:#e7ed9c;"><a href="/wiki/Transport_layer" title="Transport layer">Transport</a>
</td>
<td style="background:#e7ed9c;"><a href="/wiki/Packet_segmentation" title="Packet segmentation">Segment</a>, <a href="/wiki/Datagram" title="Datagram">Datagram</a>
</td>
<td style="background:#e7ed9c;">Reliable transmission of data segments between points on a network, including <a href="/wiki/Packet_segmentation" title="Packet segmentation">segmentation</a>, <a href="/wiki/Acknowledgement_(data_networks)" title="Acknowledgement (data networks)">acknowledgement</a> and <a href="/wiki/Multiplexing" title="Multiplexing">multiplexing</a>
</td></tr>
<tr>
<th rowspan="3">Media<br>layers
</th>
<td style="background:#eddc9c;">3
</td>
<td style="background:#eddc9c;"><a href="/wiki/Network_layer" title="Network layer">Network</a>
</td>
<td style="background:#eddc9c;"><a href="/wiki/Network_packet" title="Network packet">Packet</a>
</td>
<td style="background:#eddc9c;">Structuring and managing a multi-node network, including <a href="/wiki/Address_space" title="Address space">addressing</a>, <a href="/wiki/Routing" title="Routing">routing</a> and <a href="/wiki/Network_traffic_control" title="Network traffic control">traffic control</a>
</td></tr>
<tr>
<td style="background:#e9c189;">2
</td>
<td style="background:#e9c189;"><a href="/wiki/Data_link_layer" title="Data link layer">Data link</a>
</td>
<td style="background:#e9c189;"><a href="/wiki/Frame_(networking)" title="Frame (networking)">Frame</a>
</td>
<td style="background:#e9c189;">Transmission of data frames between two nodes connected by a physical layer
</td></tr>
<tr>
<td style="background:#e9988a;">1
</td>
<td style="background:#e9988a;"><a href="/wiki/Physical_layer" title="Physical layer">Physical</a>
</td>
<td style="background:#e9988a;"><a href="/wiki/Bit" title="Bit">Bit</a>, <a href="/wiki/Symbol_rate#Symbols" title="Symbol rate">Symbol</a>
</td>
<td style="background:#e9988a;">Transmission and reception of raw bit streams over a physical medium
</td></tr></tbody></table>


### Physical Layer

The physical layer is the lowest layer of the OSI model. This layer manages the reception and transmission of the unstructured raw bit stream over a physical medium. It describes the electrical/optical, mechanical, and functional interfaces to the physical medium. The physical layer carries the signals for all of the higher layers.

In Windows, the physical layer is implemented by the network interface card (NIC), its transceiver, and the medium to which the NIC is attached.


### Data Link Layer

The data link layer sends frames between physical addresses and is responsible for error detection and recovery occurring in the physical layer.

The data link layer is further divided by the Institute of Electrical and Electronics Engineers (IEEE) into two sublayers: media access control (MAC) and logical link control (LLC).

#### [MAC](https://learn.microsoft.com/en-US/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model#mac)

The MAC sublayer manages access to the physical layer, checks frame errors, and manages address recognition of received frames.

In the Windows network architecture, the MAC sublayer is implemented in the NIC. The NIC is controlled by a software device driver called the [miniport driver](https://learn.microsoft.com/en-US/windows-hardware/drivers/network/ndis-miniport-drivers2). Windows supports several variations of miniport drivers including WDM miniport drivers, miniport call managers (MCMs), and miniport [intermediate drivers](https://learn.microsoft.com/en-US/windows-hardware/drivers/network/ndis-intermediate-drivers).

#### [LLC](https://learn.microsoft.com/en-US/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model#llc)

The LLC sublayer provides error-free transfer of data frames from one node to another. The LLC sublayer establishes and terminates logical links, controls frame flow, sequences frames, acknowledges frames, and retransmits unacknowledged frames. The LLC sublayer uses frame acknowledgement and retransmission to provide virtually error free transmission over the link to the layers above.

In Windows, the LLC sublayer is implemented by a software driver known as a [protocol driver](https://learn.microsoft.com/en-US/windows-hardware/drivers/network/roadmap-for-developing-ndis-protocol-drivers).

### Network Layer

The network layer controls the operation of the subnet. This layer determines the physical path that the data should take, based on the following:

-   Network conditions
    
-   Priority of service
    
-   Other factors, such as routing, traffic control, frame fragmentation and reassembly, logical-to-physical address mapping, and usage accounting

The network layer is implemented by a [protocol driver](https://learn.microsoft.com/en-US/windows-hardware/drivers/network/roadmap-for-developing-ndis-protocol-drivers).

### Transport Layer

The transport layer ensures that messages are delivered error free, in sequence, and with no loss or duplication. This layer relieves the higher-layer protocols from being concerned about data transfer with their peers.

A minimal transport layer is required in protocol stacks that include a reliable network or LLC sublayer that provides virtual circuit capability. For example, because the NetBEUI transport driver for Windows is an OSI-compliant LLC sublayer, its transport layer functions are minimal. If the protocol stack does not include an LLC sublayer, and if the network layer is unreliable and/or supports datagrams (as with TCP/IP's IP layer or NWLink's IPX layer), the transport layer should include frame sequencing and acknowledgment, as well as retransmission of unacknowledged frames.

In the Windows network architecture, the transport layer is implemented by a [protocol driver](https://learn.microsoft.com/en-US/windows-hardware/drivers/network/roadmap-for-developing-ndis-protocol-drivers), which is sometimes referred to a _transport driver_.

## Overview of the different protocols

![[Pasted image 20221111140743.png]]

## Data packets

![[LAN and WAN 2022-12-20 17.46.01.excalidraw]]
### [[TCPIP protocol]]
