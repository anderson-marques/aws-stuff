# NAT Instance Config

You have been tasked to design and launch an EC2 NAT instance in a public subnet in your client's VPC. After creating and successfully testing the NAT instance. You have also updated your private subnet's route table such that the NAT device is the target for traffic destined to the Internet. However, the private subnet EC2 instances are still not able to connect to the Internet for updates and patch download.

Which of the following steps could be a possible reason for this problem?

1. NAT instance is launched with only one ENI in the public subnet
2. The NAT instance has not been configured with the proper NAT rules to process the private instance's traffic inteded for the internet
3. The NAT instance will not work, you need to configure static, one-to-one NAT on the VPC Internet Gateway for private subnet's instances to connect to the internet
4. **Disabling the Source/Destination Check attribute on the NAT instance**


Choices Analysis:

1. **Incorrect** - NAT instances can do its functions with one ENI (Primary Interface or eth0)
2. **Incorrect** - NAT AMIs has the required rules/configurations to performe the assigned PAT (Port Address Translation) job
3. **Incorrect** - NAT Instance does PAT function and this is enough to do the job required
4. **Correct** - This is one possible reason (besides checking the Security Groups and NACLs)
#
## [goback...](./vpc-questions.md)