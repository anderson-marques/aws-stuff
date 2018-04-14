# VPC Peering

You have **three separate VPCs in your AWS account in one region**, currently the VPCs are operating separately. However, a new **file sharing solution is launched in VPC-1** and you want the other two VPCs, **VPC-2, and VPC-3 resources to be able to upload and download files from this file sharing solution**.

How can you architect a solution to allow the three VPCs to share the file sharing solution? Taking into account cost effectiveness and speed of deployment.

1. Establish two peering connections between VPC-1 and VPC-2, and VPC-2 and VPC-3
2. **Establish a peering connection between VPC-1 and VPC-2, and another between VPC-1 and VPC-3**
3. Move the file sharing solution to your data center, and deploy VPN connections from each VPC to the data center
4. You can not share resources between VPCs in AWS

_Choices Analysis_:
1. **Incorrect** - VPC-2 to VPC-1 is fine, but VPC-3 can not get to VPC-1 through its peering with VPC-2
2. **Correct**
3. **Incorrect** - Costly and will take time
4. **Incorrect** - Yes, you can

**Quick refresher**:
- A VPC peering connection is a one to one relationship between two VPCs. You can create multiple VPC peering connections for each VPC that you own.
- Transitive peering relationships are not supported: you do not have any peering relationship with VPCs that your VPC is not directly peered with
- If you want to enable routing of traffic between VPC-B and VPC-C, you must create a unique VPC peering connection beetween them.


#
## [goback...](./index.md)