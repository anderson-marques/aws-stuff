# SSH Access from the Internet

Your AWS SysOps administrator created a **VPC with a public subnet**. He created and attached an **Internet Gateway to the VPC**, and launched an **EC2 instance with a public IP** in the subnet. He also **created a security group** for the EC2 instance. When **trying to connect to the EC2 instance from the Internet**, he was not able to. From the statements below, which could be a possible reason for his inability to connect?  **(Choose 2)**

1. There is no entry in the route table pointing to the internet gateway as a Target
2. The admin did not configure the security group after he created it
3. The security group is denying any outbound traffic to the Internet
4. The admin forgot to create a NACL for the EC2 instance

Options:

1. 3 and 4
2. **1 and 2**
3. 1 and 3
4. 2 and 3

_Choice Analysis_:
- **Correct** - For the subnet to the public, an destination: 0.0.0.0/0 pointing at the IGW must be present in the route table of the subnet hosting the EC2 instance
- **Correct** - Custom (non-default) security group would not have SSH allowed inbound
- **Incorrect** - Security groups alwasy allow outbound traffic by default
- **Incorrect** - Default NACL would apply in this case, which allows all inbound/outbound
#
## [goback...](./index.md)