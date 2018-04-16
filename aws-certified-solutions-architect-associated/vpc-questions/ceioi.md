# Connect to EC2 instance Over Internet

You are trying, unsuccessfully, to **connect to the EC2 instance** you just created in your AWS VPC environment. As part of your troubleshooting effort to fix this, you verified that the **VPC has an Internet Gateway (IGW) attached** to it, and that **the instance has an associated Elastic IP (EIP)**, and the **correct security group rules** are in place.

Which other VPC components should you evaluate? (Choose two)

1. The configuration of a NAT instance
2. **The configuration of the Route Table**
3. The configuration of the internet Gateway (IGW)
4. The configuration of SRC/DST checking
5. **The EC2 Instance subnet’s N. ACL configuration**

1. **2 and 5**
2. 1 and 3
3. 3 and 5
4. 3 and 4

**Quick refresher**:

- Remember, in order for a subnet to be public and for its EC2 instances to be accessible from the internet, you need to ensure that:
    - The subnet's VPC has an IGW attached to it
    - The subnet's associated route table has an entry 0.0.0.0/0 pointing at the IGW
    - Security group and NACL of the subnet both are configured properly
    - The EC2 instance has either a Public or Elastic IP (if not used with an ELB)


#
## [goback...](./index.md)