# Security Groups Defaults

Which of the below statements is true for **any VPC security group**, by default, **when it is created**?

1. All inbound traffic rule will be explicitly denied
2. All inbound traffic is allowed by default
3. **All outbound traffic is allowed by default**
4. Traffic to the internet gateway is allowed by default

Choices Analysis:

1. **Incorrect** - Security groups do not have explicity deny
2. **Incorrect** - All inbound traffic is denied by default in a Custom security group
3. **Correct** - By default there is a 0.0.0.0/0 on All protocols/ports allowed by default - outbound
4. **Incorrect** - Security Group do not have such a default rule

_Quick refresher:_

- Custom security groups in a VPC will always
    - No inbound rules - basically all inbound traffic is denied by default
    - All outbound traffic is allowed by default
- Default security groups in a default or custom VPC, will have: 
    - Inbound rules allowing Instances assigned the same security group to talk to one another
    - All outbound traffic is allowed  
- Security groups have allow only rules, no **explicit deny rules**
- A security group set of rules ends with an **implicit deny all**
#
## [goback...](./index.md)