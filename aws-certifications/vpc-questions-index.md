
#

Using **AWS direct connection, with public and private VIFs** you can: (Choose 3)

1. Connect to AWS services over the private VIF
2. Connect to your private VPC subnets over the public VIF
3. **Connect to your private VPC subnets over the private VIF, and to Public AWS services over the public VIF**
4. Substitute your internet connection at your DC with AWS’s public Internet through the use of a NAT gateway in your VPC
5. **Once connected to your VPC through Direct conect you can connect to all AZs within the region**
6. **Using IPSec VPN you can connect over the public VIF to remote AWS regions as well**

Options: 
1. 1, 2 and 3
2. 3, 4 and 5
3. **3, 5 and 6**
4. 2, 3 and 4

_Choice Analysis_:
1. **Incorrect** - This can be done over the public VIF
2. **Incorrect** - This can be done over the private VIF
3. **Correct** - 
4. **Incorrect** - You can't access the AWS internet through the Direct Connect Connection
5. **Correct** - 
6. **Correct** - 

**Quick refresher**:
- DX is a direct connection (not internet based) and **provides for higher speeds (bandwidth), less latency and higher performance** than Internet
- A Virtual Interface (VIF) is basically a 802.1Q VLAN mapped from the customer router to the Direct Connect router
- You need one private VIF to connect to your private VPC subnets, and one public VIF to connect your AWS public services
- You **CANNOT** establish layer 2 over your DX connection
- You **CANNOT** use a NAT instance/gateway in your VPC over the direct connect connection
#
## [goback...](./vpc-questions.md)
#

Your company has **peered two VPCs in the same region, VPC-A and VPC-B**. Moreover, **your company’s HQ is connected to VPC-A using a VPN connection**. You want to make this setup more **fault tolerant**, and ensure that company HQ has connectivity to VPC-A at all times.

How can you architect this solution **quickly and cost effectively**?

1. Peer the corporate network to VPC-B
2. Connect Corporate network to VPC-B by a VPN connection such that it has another path to VPC-A
3. **Configure a second VPN connection between HQ and VPC-A from another customer gateway at the HQ**
4. Configure a second VPC peering between VPC-A and VPC-B

**Important question points**:
- Solution is not fault tolerant as it stands
- HQ connectivity to VPC-A is critical
- Solution needs to be quick to deploy and cost effective

_Choices Analysis_:
1. **Incorrect** - You **CANNOT** do VPC peering between a VPC and an external network
2. **Incorrect** - Edge to Edge routing is not supported - HQ can't access VPC-A through VPC-B
3. **Correct** - 
4. **Incorrect** - You can not configure a second peering connection between two VPCs

**Quick Refresher**:
- VPC peering does not support edge-to-edge routing.
- VPC-A and VPC-B are peered, VPC-A is also connected to the Corporate Network by a VPN or Direct Connect Connection
- Corporate network **CANNOT** access VPC-B by being connected to VPC-A, because VPC peering will not allow VPC-B routes to be advertised to Corporate network and vice versa
- Edge to edge routing here refers to routing external traffic (to the peered VPCs) through the VPC peering connection
#
## [goback...](./vpc-questions.md)
#

Your company has **seven offices including HQ**. The company just implemented an application on AWS in a VPC. The application will be **accessed by company employees from all seven locations**. Latency and performance **are not a big concern**, however, the solution needs to be **fast, easy to deploy, and cost effective**.

How would you architect the solution?

1. Deploy an OpenSSL server on an EC2 instance in your VPC. Have the employees establish SSL based remote access when they need to access the application
2. **Establish a site-to-site IPSec VPN from each location to the VPC’s VGW and adjust routing to allow access to the application**
3. Establish a Direct Connect connection from each location to the VPC
4. You can not connect multiple locations concurrently to your AWS VPC

_Choice Analysis_:

1. **Incorrect** - despite possible but this involves an EC2 instance, administration hassle
2. **Correct** - VPN CloudHub is the solution to this case
3. **Incorrect** - Costly and not quick
4. **Incorrect** - You can

**Quick Refresher**:
- You can **have up to 10 IPSec** connections per VGW (soft limit can be increased by contacting AWS)
- VPN based Hub and Spoke connectivity to a common VGW
- Can mix DX connections with VPN connections
- Spokes can communicate with each other and with the VPC

#

Your company just implemented an HR application on **AWS in a VPC**. The application will provide payroll and benefits information to the employees and **needs to be accessed from all twenty Company locations**. Latency and performance **are not a big concern**, however, the solution needs to be **fast and easy to deploy and cost effective**. Your solutions should also allow the **twenty locations to communicate with one another**.

How would you architect the solution?

1. Deploy an OpenSSL server on an EC2 instance in your VPC. Have the employees establish SSL based remote access when they need to access the HR application
2. Establish a site-to-site IPSec VPN from each location to the VPC’s VGW and adjust routing to allow access to the application
3. You can not connect multiple locations concurrently to your AWS VPC
4. **You need to contact AWS first to increase the 10 VPNs per VGW limit, then configure VPN Cloudhub to connect the 20 locations**

_Choice Analysis_:

1. **Incorrect** - Requires EC2 instance and administration hassle. Also it is not site-to-site
2. **Incorrect** - By default AWS allows only 10 VPN connections per VGW
3. **Incorrect** - Costly and not quick
4. **Correct**  
#
## [goback...](./vpc-questions.md)