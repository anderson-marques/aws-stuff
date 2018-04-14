# VPC Peering and VPN Connection

Your company has **peered two VPCs in the same region, VPC-A and VPC-B**. Moreover, **your company’s HQ is connected to VPC-A using a VPN connection**. You want to make this setup more **fault tolerant**, and ensure that company HQ has connectivity to VPC-A at all times.

How can you architect this solution **quickly and cost effectively**?

1. Peer the corporate network to VPC-B
2. Connect Corporate network to VPC-B by a VPN connection such that it has another path to VPC-A
3. **Configure a second VPN connection between HQ and VPC-A from another customer gateway at the HQ**
4. Configure a second VPC peering between VPC-A and VPC-B

**Important question points**:
- Solution is not fault tolerant as it stands
- HQ connectivity to VPC-A is critical
- Solution needs to be quick to deploy and cost effective

_Choices Analysis_:
1. **Incorrect** - You **CANNOT** do VPC peering between a VPC and an external network
2. **Incorrect** - Edge to Edge routing is not supported - HQ can't access VPC-A through VPC-B
3. **Correct** - 
4. **Incorrect** - You can not configure a second peering connection between two VPCs

**Quick Refresher**:
- VPC peering does not support edge-to-edge routing.
- VPC-A and VPC-B are peered, VPC-A is also connected to the Corporate Network by a VPN or Direct Connect Connection
- Corporate network **CANNOT** access VPC-B by being connected to VPC-A, because VPC peering will not allow VPC-B routes to be advertised to Corporate network and vice versa
- Edge to edge routing here refers to routing external traffic (to the peered VPCs) through the VPC peering connection
#
## [goback...](./index.md)