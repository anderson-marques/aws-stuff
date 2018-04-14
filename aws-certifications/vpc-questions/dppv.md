# DX, public and private VIFs

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
## [goback...](./index.md)