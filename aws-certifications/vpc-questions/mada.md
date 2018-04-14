# Multi AZs DX Access

Your client has a **multi AZ infrastructure on AWS**, and plans , in few months, to have a centralized, custom, dashboard **in the client’s data center**. The dashboard will need to interact with the multi AZ infrastructure. Data from the Multi AZ will be pulled from the data center. **Latency and performance (bandwidth) are key**. The solution needs to be up and running **within few months**.

How would you architect the solution?

1. Use redundant VPN connections to two VGW routers in the region, this should give you access to the infrastructure in all AZs
2. **Use direct connect connection to the client VPC, as this will provide access to all AZs in the region, and will also provide better bandwidth and lower latency**
3. Use one direct connect connection from the data center to each AZ in the region
4. You cannot interact with multiple AZs from one location

**Important question points**:
- Multi AZ infrastructure on AWS that will be connected to the client daa center
- Time frame is few months
- Solution must allow the data center to pull data from multiple AZs
- Requires bandwidth and latency guarantees

_Choices Analysis_:
1. **Incorrect** - VPN will not guarantee bandwidth and latency, it is Internet based
2. **Correct** - 
3. **Incorrect** - You do not need a DX connection per AZ
4. **Incorrect** - You can
#
## [goback...](./vpc-questions.md)