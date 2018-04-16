# VPN CloudHub - Seven locations

Your company has **seven offices including HQ**. The company just implemented an application on AWS in a VPC. The application will be **accessed by company employees from all seven locations**. Latency and performance **are not a big concern**, however, the solution needs to be **fast, easy to deploy, and cost effective**.

How would you architect the solution?

1. Deploy an OpenSSL server on an EC2 instance in your VPC. Have the employees establish SSL based remote access when they need to access the application
2. **Establish a site-to-site IPSec VPN from each location to the VPC’s VGW and adjust routing to allow access to the application**
3. Establish a Direct Connect connection from each location to the VPC
4. You can not connect multiple locations concurrently to your AWS VPC

_Choice Analysis_:

1. **Incorrect** - despite possible but this involves an EC2 instance, administration hassle
2. **Correct** - VPN CloudHub is the solution to this case
3. **Incorrect** - Costly and not quick
4. **Incorrect** - You can

**Quick Refresher**:
- You can **have up to 10 IPSec** connections per VGW (soft limit can be increased by contacting AWS)
- VPN based Hub and Spoke connectivity to a common VGW
- Can mix DX connections with VPN connections
- Spokes can communicate with each other and with the VPC
#
## [goback...](./index.md)