# High Availability DX

Your client plans to **connect their Data Center to their AWS VPC** in preparation for an application launch in **few months**. The application they are launching is chatty and has components in AWS and in the data center, and **will be hosted in private AWS subnets in their AWS VPC**. It also **requires bandwidth and latency guarantees at all times**. The solution has to be **fault tolerant**. Which connectivity method would you recommend for them?

1. One VPN connection with two tunnels between one Customer Gateway and one VGW router on AWS side
2. Two Public VIFs over two Direct connect connections. From two Customer routers to two different DX routers
3. **Two Direct connect connections using two Customer routers and two private VIFs to two different Direct connect routers**
4. One direct connect connection with one private VIF, and a backup VPN connection from two customer routers

**Important question points**:
- Application requires bandwidth and latency guarantees
- Application will be hosted in private subnets in the VPC
- Solution must be fault tolerant
- Application will launch in few months (They have time)
- Single choice

_Choices Analysis_:
- 1. **Incorrect** - VPN will not guarantee bandwidth and latency, it is Internet based
- 2. **Incorrect** - The application will be hosted in private subnets, you need private VIF
- 3. **Correct** - 
- 4. **Incorrect** - VPN backup will not provide bandwidth and latency guarantees
#
## [goback...](./vpc-questions.md)