# VPN SSH Access

Using the VPC wizard, you have created a VPC with CIDR 10.0.0.0/16 with a VPN-only private subnet and Hardware VPN Access connection. You need to connect to an instance in the private subnet over SSH.

How should you define the instance’s security group rule to allow SSH?

1. **Allow Inbound traffic for SSH (port 22) from the corporate network**
2. Allow port 22 on the security group of the VPN-only subnet to allow SSH inbound
3. Create a public subnet, Implement a NAT instance and use it to connect to the VPN-only subnet instances
4. Allow Inbound traffic on port 22 to allow you to connect to a private subnet over the Internet

Choices Analysis:
1. **Correct** - From the corporate network, connect to the private subnet over port 22
2. **Incorrect** - There is no such a thing as security group of a VPN subnet
3. **Incorrect** - NAT instances are not for Internet Initiated connections
4. **Incorrect** - The VPC has not been configured with a public subnet for Internet Access
#
## [goback...](./vpc-questions.md)