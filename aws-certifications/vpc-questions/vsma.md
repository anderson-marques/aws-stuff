# VPC Subnets and muilti-AZ

A company wants to implement their website in a **virtual private cloud (VPC)**. The web tier will use an Auto Scaling group across multiple Availability Zones (AZs). The database will use Multi-AZ RDS MySQL and should not be publicly accessible.

What is the minimum required number of VPC subnets to achieve this?

1. 1 subnet
2. 2 subnets
3. 3 subnets
4. **4 subnets**

**Remember**:
- In a VPC a subnet is bound to an AZ, you can NOT have a subnet stretch over multiple AZs
- To have instances that are Internet accessible, you need to launch them in a public subnet
    - The public subnet must be in a VPC that has an IGW attached to it
    - The subnet's rout table must have an entry pointing at the IGW for default route (0.0.0.0/0)
- If you require to have Instances that are not accessibleto the internet, you need to launch these in private subnets
- If you want muilti-az in your architecture, the minimun is to have your infrastructure deployed over two AWS Availability Zones
- EC2 instances served by an internet-facing ELB can be in a public or private subnet

#
## [goback...](./index.md)