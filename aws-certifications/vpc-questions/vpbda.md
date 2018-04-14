# VPC Peering Between different accounts

Your company has entered an agreement with two other vendors to jointly sell each other’s line of products. **All three are using VPCs in AWS in the same region**. Agreement is, **each of the three companies can directly access stock and pricing information of this line of products from the other VPCs**. The EC2 instances hosting stock and pricing information in the the three VPCs’ are on non-overlapping IP subnets.

How can you architect this solution **quickly and cost effectively**?

1. Implement an AWS direct connection in a full mesh between the three VPCs
2. Use one of the three company VPCs as a hub and implement a VPN Cloud hub using VPN connections from the other two VPCs
3. **Create a full mesh VPC peering connections between the three VPCs and adjust your routing tables to enable traffic flow between them**
4. These are different AWS accounts and you can not create VPC peering between them

_Choices Analysis_:
1. **Incorrect** - Direct connection is intended for connecting on-premises to your VPC(s)
2. **Incorrect** - VPC peering does not support transitive peering
3. **Correct**
4. **Incorrect** - You can configure peering connections between VPC in different AWS accounts (on same region)




#
## [goback...](./index.md)