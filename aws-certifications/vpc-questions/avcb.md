# Additional VPC CIDR blocks

You have created a VPC with CIDR 10.0.0.0/24. The VPC has two subnets: public (10.0.0.0/25) and private (10.0.0.128/25). For an anticipated project you want to increase the CIDR range your VPC CIDR block, How can you do this?

1. Change the subnet sizes to /28 subnets, then you will have more room to grow your VPC CIDR
2. You can always change a VPC's original CIDR block as needed
3. You can add additional VPC CIDR blocks, but can’t change the existing one
4. Delete all the subnets first, only then you can modify the size of the VPC

Choices Analysis:
1. **Incorrect** - VPC CIDR block can not be changed. 
2. **Incorrect** - VPC CIDR block can not be changed. 
3. **Correct** - You can add additional VPC CIDR blocks, but can't change the existing one
4. **Incorrect** - You still can't change the VPC CIDR
#
## [goback...](./vpc-questions.md)