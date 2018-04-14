# How to allow traffic to the Internet

You created **a subnet in a custom VPC** and launched **an EC2 instance** in that subnet. During the EC2 instance creation, using AWS console, **you did not choose the option to assign a public IP address to your instance**. This instance now **needs access to the Internet**, but it **has no public IP address**.

How would you solve this internet connectivity issue for this EC2 instance?

1. The instance will always have a public DNS attached to the instance by default
2. Allocate and attach an Elastic IP directly to the instance
3. The instance would not launch if the public IP is not assigned
4. **Create an internet gateway, attach it to the VPC, do the needed route table configuration for a public subnet. Adjust security group, and NACLs configurations to facilitate this, and finally, attach an elastic IP to the instance to connect to the Internet**

_Choice Analysis_:
1. **Incorrect** - This depends on the instance, how many interfaces, public IP assigned or not.. etc
2. **Incorrect** - Public and Elastic IP addresses are configured on the IGW and NAT'ed to the Instance's private IPv4 address
3. **Incorrect** - Instances can launch in Private subnets without a public IP
4. **Correct** - These are the steps needed to allow traffic to the Internet

**Quick Refresher**:
- In order for an instance to be access or access the Internet:
    - It has to be in a public subnet with a Public or Elastic IP
        - A public Subnet is a subnet created which has:
            - A route table with an Entry to an Internet Gateway
            - The Internet Gateway must be attached to the VPC
            - Security group and NACL must allow the traffic as necessary
#
## [goback...](./index.md)