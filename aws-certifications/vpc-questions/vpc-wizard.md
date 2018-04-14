# VPC Wizard

When using the **VPC wizard to create a VPC** with **private and public subnets**, which of the below statements stands **correct**? **(Choose two)**

1. AWS VPC will automatically create a NAT instance with the micro size
2. **VPC bounds the main route table with a private subnet and a custom route table with a public subnet**
3. **User has to select a NAT instance instead of the NAT gateway if needed during the wizard configuration**
4. VPC bounds the main route table with a public subnet and a custom route table with a private subnet

Options:

1. **2 and 3**
2. 3 and 4
3. 1 and 2
4. 2 and 4

_Choices Analysis_:
1. **Incorrect** - AWS VPC Wizard configures a NAT gateway unless you change this to NAT instance
2. **Correct** - Main to the private, Custo to the public
3. **Correct**  
4. **Incorrect** - This is the opposite to what happens, Invalid Answer

**Quick Refresher**:
- For VPC Wizard configurations, when a public and private subnets are created, two route tables are created by AWS for you. The main VPC route table, which gets assigned to the Private IPv4 subnet and a Custom route table, which gets assigned to the public IPv4 subnet.
- The VPC will have an Internet Gateway (IGW) created and attached
- Private subnet, associated with the main route table, will have a NAT gateway (you can change it during the wizard configuration to a NAT instance) to access the internet.
- The NAT instance type by defaults is m1-small (you can choose otherwise but not less than m1-small)
#
## [Goback...](./index.md)