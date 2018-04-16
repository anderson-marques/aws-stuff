# AWS Console - Deleting a VPC

One of the AWS administrators created **a VPC with CIDR 10.0.0.0/16**, a **public and VPN-only subnets** with hardware VPN access using the **VPC wizard**. She has just created the VPC and did not launch any instances, nor has she modified anything after the VPC was launched. Now she **wants to delete this VPC using the AWS console**.

How can she achieve this?

1. The console will delete the VPC, its components including the Virtual Private Gateway
2. The console will request detaching the Virtual Private Gateway first, then would allow deleting the VPC
3. **The console will delete the VPC, its components, and will also detach the Virtual Private Gateway**
4. She can’t since the NAT instance is running

_Choice Analysis_:
1. **Partially correct** - Console will not delete the VGW
2. **Incorrect** - Console will delete without asking the user
3. **Correct** - Console will delete the setup and detach the VGW
4. **Incorrect** - No NAT instances gets created for Public, and VPN-only subnets VPC. It was not mentioned. Private subnet with VPN-only connection does not have a NAT instance. It is nonsense.

**Information that is not important:**
- VPC CIDR

**Quick Refresher**:
- When you launch a VPC with public, VPN only subnets and a hardware VPN, the following also gets created
    - VGW
    - VPN connection is defined and created
- You can delete this VPC, everything will be deleted except VGW and VPN connection
    - VGW will be detached from the VPC
    - VPN connection wil still be using the VGW
        - To delete the VGW you have to delete the VPN connection first
#
## [Goback...](./index.md)