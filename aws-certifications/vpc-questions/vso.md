# VPC subneting overlaping

After creating a **VPC with CIDR 10.0.0.0/16**. with the lack of proper architecture, The AWS SysOps admin created one large **subnet of CIDR 10.0.0.0/16**. later on, another subnet was needed to host another tier of an application being deployed. The admin is **trying to create another subnet of CIDR 10.0.1.0/24**.

Can she create the second subnet without disrupting services to the first subnet?

1. Yes, she can configure the new subnet, and AWS will automatically adjust the VPC subnets so both can exist.
2. Yes, Edit the fist subnet from the console to make room for the second one
3. **No, It is not possible to create a second subnet as the intended one overlaps with the existing one.**
4. Yes, Delete the VPC and create a new one

_Choice Analysis_:

1. **Incorrect** - AWS VPC does not adjust subnets automatically
2. **Incorrect** - You can not adjust subnet size after creating it, you can delete it and create another
3. **Correct** - The first one took all the VPC CIDR block, hence, any other one will overlapping with it
4. **Incorrect** - Although this would work, but this would cause a major impact to the services/apps

**Quick Refresh**:
- You cannot create overlapping IP address subnet in a VPC
- All VPC subnets must be no-overlapping
- If you create one subnet equal in size to the VPC CIDR block, you will not be able to crete any other subnet in the VPC because any other one that belongs to the CIDR block will overlap with the first one
    - Solution - delte the one you created, and then carefully design and deploy your IP address scheme
#
## [goback...](./index.md)