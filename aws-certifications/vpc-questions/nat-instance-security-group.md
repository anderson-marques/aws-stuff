# NAT instance Security Group

You created a **VPC with both public and private subnets**. The **VPC CIDR is 10.0.0.0/16**. The **private subnet is 10.0.1.0/24** and the **public subnet is 10.0.0.0/24**. The goal is to host a web server int the public subnet **receiving traffic on port 80**, and a DB server in the **private subnet receiving traffic on port 3306**. The database server will require in-frequent Internet access for patching and updates. When you are configuring the **security group of the NAT instance (NATSG)**, which of the below mentioned entries is not required?

1. Allow Source: 10.0.1.0/24, Direction: Inbound, Port: 80
1. Allow Destination: 0.0.0.0/0, Direction: Outbound, Port: 80
1. **Allow Source: 10.0.0.0/24, Direction: Inbound, Port: 80**
1. Allow Destination: 0.0.0.0/0, Direction: Outbound, Port: 443

Choices Analysis:

1. **Correct** - In order to allow private subnet request to NAT
2. **Correct** -In order to NAT request to the Internet
3. **Incorrect** - Public Subnet does not need use NAT
4. **Correct** - In order to NAT request to the Internet using SSL/TLS

_Quick refresher:_
- Security groups have inbound and outbound rules
- Security groups can only have Allow rules
- Draw in your mind, to understand the scenario better
- Focus on Inbound and Outbound traffic
- Private subnet instances will want to access websites on the internet (HTTP or HTTPs)
- Internet destinations when are not listed has to have 0.0.0.0/0 for all internet destinations
- NAT instances serves the private subnet's instances and not the public subnet's instances
#
## [goback...](./vpc-questions.md)