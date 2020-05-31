---
title: 02 - OSI Model and TCP/IP Model
created: '2020-05-31T17:18:59.178Z'
modified: '2020-05-31T21:16:16.974Z'
---

# 02 - OSI Model and TCP/IP Model

- The **I**nternational **O**rganization for **S**tandardization (ISO) is responsible for making stardards different devices can rely on for communicating.

- The **O**pen **S**ystems **I**nterconnection (OSI) model supported by ISO was competing against the TCP/IP model supported by the US Department of Defense. The latter became the industry standard. Both provide us with a layered approach to the network.

## The OSI and TCP/IP model

TCP/IP Layers (1) to (3) are critical for a network engineer.

<table>
	<tr>
		<th>Protocol Data Unit</th>
		<th>TCP/IP Layer</th>
		<th>OSI Layer</th>
		<th>Function</th>
	</tr>
	<tr>
		<td rowspan="3">Data</td>
		<td rowspan="3">(4) Application</td>
		<td>(7) Application</td>
		<td>Communicates with "Network Aware" applications (ftp, dns, etc)</td>
	</tr>
	<tr>
		<td>(6) Presentation</td>
		<td>"Generifies" data, data conversion, encryption service (ssl, etc)</td>
	</tr>
	<tr>
		<td>(5) Session</td>
		<td>Creates and maintains sessions (ftp, telnet, etc)</td>
	</tr>
	<tr>
		<td>Segment</td>
		<td>(3) Transport</td>
		<td>(4) Transport</td>
		<td>Reliable (TCP), unreliable (UDP), port</td>
	</tr>
	<tr>
		<td>Packet</td>
		<td>(2) Network</td>
		<td>(3) Internet</td>
		<td>IP adressing, finding the best path</td>
	</tr>	
	<tr>
		<td>Frame</td>
		<td rowspan="2">(1) Network Interface</td>
		<td>(2) Data link</td>
		<td>MAC addressing, error checking</td>
	</tr>
	<tr>
		<td>Bit</td>
		<td>(1) Physical</td>
		<td>Actual data transfer (wires, cables, etc)</td>
	</tr>
</table>

- "Please Do Not Throw Sausage Pizza Away"
- "TCP/IP comes in A TIN"

While communicating, each layer adds its header. When some data is transmitted from a device (a) to (b) in UDP, the following happens in the first device:
1. - |TH|Seg1| --- |TH|Seg2|
2. - |TH|Seg2|
   - |NH|TH|Seg1|
3. - |NH|TH|Seg2|
   - |DH|NH|TH|Seg1|
4. - |DH|NH|TH|Seg2|
   - Binary data Seg1 transmitted to (b)
5. - Binary data Seg2 transmitted to (b)

Then the opposite happens at (b). The transport layer will wait to receive the whole data, here Seg1 and Seg2, before giving it to upper layers.
