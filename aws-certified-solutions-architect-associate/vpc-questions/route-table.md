# VPC Route Table - Communication Between Subnets

You used the **VPC wizard** to create **a VPC with public and private subnets**. The **VPC CIDR is 10.0.0.0/16**, and the the **private subnet CIDR is 10.0.0.0/24**.

Which of the below **main route table entries** is required to allow the instances in the VPC to communicate with one another?

1. Destination : 10.0.0.0/24 and Target : VPC
2. Destination : 10.0.0.0/16 and Target : ALL
3. Destination : 10.0.0.0/0 and Target : ALL
4. **Destination : 10.0.0.0/16 and Target : Local**

_Choice Analysis_:
1. There is nothing in the route tables that has an entry pointing at the VPC as a whole
2. Target "ALL" is not a valid Target for Route tables
3. Target "ALL" is not a valid Target for Route tables
4. This is the entry that is created by default in "any" route table to allow all VPC subnets to communicate with one another

#
## [Goback...](./index.md)