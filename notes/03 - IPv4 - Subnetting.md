---
title: 03 - IPv4 - Subnetting
created: '2020-05-31T22:43:46.470Z'
modified: '2020-06-01T08:19:14.071Z'
---

# 03 - IPv4 - Subnetting

The need for subnetting arouse when it was realized there won't be enough IP addresses for every device on the network. **Public** and **private** IP addresses then appeared.

When **subnetting**, one uses **C**lassless **I**nter-**D**omain **R**outing (CIDR) notation. 

## Class C Subnetting
To devide a network in two subnets, one can make use of a special subnet mask:
- **Subnet mask**: 11111111.11111111.11111111.10000000
- **CIDR notation**: 192.168.100.0/25

The block size is 2^7 - 2 = 126 hosts. There are now two subnets:
1. - **Network Id 1**: 192.168.100.0
   - **Broadcast Id 1**: 192.168.100.127
2. - **Network Id 2**: 192.168.100.128
   - **Broadcast Id 2**: 192.168.100.255

Possible configurations:
<table>
  <thead>
    <tr>
      <th>Borrowed bits</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
      <th>5</th>
      <th>6</th>
    </tr>
  </thead>
  <tbody>
    <tr>
    	<th>Mask Value</th>
    	<td>128</td>
    	<td>192</td>
    	<td>224</td>
    	<td>240</td>
    	<td>248</td>
    	<td>252</td>
    </tr>
    <tr>
    	<th>Subnets</th>
    	<td>2</td>
    	<td>4</td>
    	<td>8</td>
    	<td>16</td>
    	<td>32</td>
    	<td>64</td>
    </tr>
    <tr>
    	<th>Hosts</th>
    	<td>126</td>
    	<td>62</td>
    	<td>30</td>
    	<td>14</td>
    	<td>6</td>
    	<td>2</td>
    </tr>
    <tr>
    	<th>CIDR</th>
    	<td>/25</td>
    	<td>/26</td>
    	<td>/27</td>
    	<td>/28</td>
    	<td>/29</td>
    	<td>/30</td>
    </tr>
    <tr>
    	<th>Block Size</th>
    	<td>128</td>
    	<td>64</td>
    	<td>32</td>
    	<td>16</td>
    	<td>8</td>
    	<td>4</td>
    </tr>
  </tbody>
</table>

### Example

- **IP Address**: 192.168.100.225
- **Subnet mask**: 255.255.255.192
- Subnet mask: 11111111.11111111.11111111.11000000

There are now four subnets with 2^6 - 2 = 62 available hosts. CIDR notation: 192.168.100.0/26.
