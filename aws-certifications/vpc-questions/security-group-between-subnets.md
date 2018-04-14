# Security Group Between Subnets

Your client has a **VPC with public and private subnets** created by the **VPC wizard**. The **VPC CIDR is 10.0.0.0/16**. The **public subnet is 10.0.1.0/24**. The architecture you put together includes deploying a web server in the public subnet, receiving **HTTP traffic on port 80**; it also includes a Database server tier in the **private subnet receiving traffic on port 3306**. The client SysOps is configuring a **security group for the public subnet** called **WebSG**, and the private subnet's security group called **DbSG**.

Which of the below entries is required in the web server security group?
1. **Destination: DB Security group ID (DBSG), Port: 3306, Direction: Outbound**
2. Destination: 0.0.0.0/0, Port: 80, Direction: Outbound
3. Source 10.0.1.0/24, Port: 3306, Direction: Inbound
4. Source 10.0.0.0/16, Port: 80, Direction Inbound

Choices Analysis:

1. **Correct** - This allows the DbSG to be the destionation on port 3306, it allows traffic destined to instances in the DbSG with a destination port 3306 (DB port)
2. **Incorrect** - The web layer will be receiving HTTP traffic from the internet, not sending it out to the Internet
3. **Incorrect** - CIDR 10.0.1.0/24 was not mentioned in the question body.
4. **Incorrect** - HTTP traffic will not be received on WebSG from the public subnet

_Quick refresher:_
- You can use Security Group names as the source of destination in other security group rules
- You can use the security group name as the source in its own inbound security group rules
- Security groups are directional and can use allow rules only
- A security group set of rules ends with an implicit deny any

#
## [goback...](./vpc-questions.md)