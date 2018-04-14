# Scalability Issue - Small subnet and ELB instances

Your client deployed a **three-tier web application** in a VPC with a **CIDR block of 10.0.0.0/27**. The client launched **four web servers behind an ELB**, **four application servers**, **two database servers**, and **two NAT instances** are already deployed in the VPC across two AZ's, for a total of **twelve EC2 instances**. Route53 is used as the DNS. When trying **to double the existing fleet of web/app instances** to keep up with the gradual increase in web traffic, not all the required instances were created/launched successfully.

Which of the following could be the root cause? (Choose 2)

1. The IP address reserved by AWS services in each subnet for DNS has taken some of the available IP addresses in each subnet, hence, why instances failed to launch.
2. **ELB scaled up to keep up with the web tier load, which created more ELB nodes, taking more of the available IP addresses in the subnet where ELB is defined**.
3. **AWS reserves the first four and the last IP address in each subnet's CIDR block so you do not have enough addresses left to launch all of the new EC2 instances**.
4. New instances failed to launch because the incoming web traffic caused the existing instance CPU utilization to increase and the request could not get through.

Choices Analysis:

1. **Incorrect** - AWS reserves more than one IP 
2. **Correct** - ELB use until 5 instances to scale up or down
3. **Correct** - AWS reserves these IPs in each subnet
4. **Incorrect** - Non sense. CPU utilization do not have importance in this scenario

_Quick refresher:_
- When an ELB is deployed in a VPC, the ELB service itself launches ELB nodes. Depending on your traffic increase, the ELB service will continue to launch new ELB nodes eating up from your subnet available IP addresses, in the subnet where you defined the ELB in each AZ
    - The more the traffic, the more IP addresses are taken from your subnet available IP's
    - AWS suggests that you account for up to 8 IP addressess in an AZ for scaling
- The subnet is bound to an AZ, and can not stretch between AZ's
- In a /28 subnet in a VPC, you actually have only 11 IP addresses available for instances and ELB

#
## [goback...](./index.md)