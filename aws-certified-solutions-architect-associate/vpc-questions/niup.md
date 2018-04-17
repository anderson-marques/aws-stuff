# NAT Instance use as Proxy

Your company just partnered with an online training provider. You got assigned the task to architect the solution. The online training provider requested, for security reasons, **that any traffic originated from your company’s AWS environment and destined to the online provider, be sourced from a maximum of one or two fixed public IP addresses**. Your AWS application instances, that should originate this traffic, are **behind an ELB**. **Auto Scaling** is also used to increase the application layer instances **from 2 to 8 depending on the traffic load** received from the ELB. The solution must be **highly available**.

How would you architect the required solution?

1. Assign two EC2 instances fixed public IPs, force the other instances to send their online provider traffic to these two instances all the time.
2. **Configure two NAT instances, one per AZ. Allocate and attach Elastic IP addresses to these instances, route the application EC2 instances traffic destined to the online provider through these two NAT instances, and provide the two Elastic IP addresses to your provider as the fixed source public IPs**
3. Use Elastic IPs on the VPC Internet Gateway Public IP since all Internet Traffic passes through them
4. Use the ELB public IP addresses as the first IP addresses required

_Choices Analysis_:
1. **Incorrect** - There are no fixed public IPs.
2. **Correct** - This can be a good solution to fix two IP addresses, also NAT can do PAT function
3. **Incorrect** - EIP is for instances not for IGW
4. **Incorrect** - ELB is for inbound traffic. Not outbound.

**Quick Refresher**:
- NAT instance in a VPC can be used with a public IP address or an Elastic IP address
- NAT instance does a PAT function, so it can hide more than one device/EC2 instance
- NAT instance is a user responsability and is not a managed AWS service (unlike the NAT gateway)
- NAT instances can be deployed across AZ's independently for High Availability. EC2 instances, in each AZ, on private subnet requiring NAT should be configured to use the local NAT instance in the respective AZ.

#
## [goback...](./index.md)