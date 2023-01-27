# ec2inVPS

In this lab I will create a Virtual Private Cloud (VPC), subnets across multiple AZ's, routes and an internet gateway.

Architecture looks like:

![alt text](/assets/architecture.png)

Once logged to AWS Management Console, go to VPC--> Create VPC

Whenever you create a VPC you must specify a range of IP addresses. /16 means there is support for over 65,000 IP addresses.

![alt text](/assets/vpc1.png)

And the rest of the settings can stay at default.
And for Tenancy — this means we are sharing hardware compared to having our own dedicated hardware.

Click create VPC… and success! Its that easy to setup a VPC.

![alt text](/assets/vpc2.png)

Step 2: Creating a public subnet
Select subnets on the left side then create subnet

![alt text](/assets/vpc3.png)

The rest configuration:

![alt text](/assets/vpc4.png)

Subnet still is not public, it must route traffic via an internet gateway.

We are here in the architecture

![alt text](/assets/arch1.webp)