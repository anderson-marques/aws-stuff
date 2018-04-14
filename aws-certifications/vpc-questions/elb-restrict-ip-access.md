# Restrict Access for some IPs

What can you do to ensure that only a specific list of Internet IP addresses can access your web tier, of two tier application you are hosting at AWS VPC. Your web servers will be served by an Internet-facing Elastic Load Balancer (ELB).

Which two ways of the below would allow you to accomplish this (Choose 2 answers)

1. Configure the VPC internet gateway to allow incoming traffic from these IP addresses
2. **Configure your ELB to send the X-forwarded for headers and web servers to filter traffic based on the ELB's "X-forwarded-for" header.**
3. **Configure the ELB security group to allow traffic from this list of IPs and deny all outbound traffic**
4. Configure a VPC NACL to allow web traffic from the list of IPs and deny all outbound traffic.

Choices Analysis:

1. **Incorrect** - IGW is an AWS services and customer do not have access to it
2. **Correct** - If the web app can do this level of control
3. **Correct** - ELB can have a security group assigned which can be configured with Allow rules for Customer's IP addresses
4. **Incorrect** - NACL is stateless if you deny all outbound traffic the return traffic will be dropped

_Quick refresher:_

- ELB can be assigned a Security Group
- ELB can be configured to forward the client/initiator's information including source IP address using `X-Forwarded-For` headers

#
## [goback...](./vpc-questions.md)