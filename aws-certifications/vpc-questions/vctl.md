# VPN CloudHub - 20 Locations

Your company just implemented an HR application on **AWS in a VPC**. The application will provide payroll and benefits information to the employees and **needs to be accessed from all twenty Company locations**. Latency and performance **are not a big concern**, however, the solution needs to be **fast and easy to deploy and cost effective**. Your solutions should also allow the **twenty locations to communicate with one another**.

How would you architect the solution?

1. Deploy an OpenSSL server on an EC2 instance in your VPC. Have the employees establish SSL based remote access when they need to access the HR application
2. Establish a site-to-site IPSec VPN from each location to the VPC’s VGW and adjust routing to allow access to the application
3. You can not connect multiple locations concurrently to your AWS VPC
4. **You need to contact AWS first to increase the 10 VPNs per VGW limit, then configure VPN Cloudhub to connect the 20 locations**

_Choice Analysis_:

1. **Incorrect** - Requires EC2 instance and administration hassle. Also it is not site-to-site
2. **Incorrect** - By default AWS allows only 10 VPN connections per VGW
3. **Incorrect** - Costly and not quick
4. **Correct**  
#
## [goback...](./index.md)