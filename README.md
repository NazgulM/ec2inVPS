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

Now onto step 3. Creating routes and configuring the Internet Gateway.

Routing inside of a VPC which defines the movement of traffic within the subnets and to and from the internet.

Select the Subnet that  created and drag up the settings. Then select Edit subnet settings

We are enabling this setting here:

![alt text](/assets/vpc4.webp)

Now onto configuring the internet gateway. This enables communication over the internet.

Select internet gateways on the left side, then create internet gateway on the right of the next page.

All I do on the next age is edit the name tag, then click create.

![alt text](/assets/vpc5.png)

Now let’s go to actions and attach to the VPC

![alt text](/assets/vpc6.webp)

All we do here is select our VPC and click attach internet gateway.

![alt text](/assets/vpc7.webp)

Now to configure routing. All this does is tells the traffic in the public subnet how to get to the internet.

You’ll notice a default route table created. That default route table allows traffic to pass to other nodes on the network but not outside the network. So, we will create the one for the public internet access.

To do this click on create route table in the top right corner.

Type in the name you wish to give it and select the VPC to use for this route table. Then click create — edit routes — add route.
This IP 0.0.0.0/0 just means the public internet.

![alt text](/assets/vpc8.webp)

Now click Save.

Our final step is to associate this public route table with our public subnet.

We’ll click on subnet associations tab — edit subnet associations — select our subnet we created and click save. Now our public subnet will allow traffic within it.

Step 4. Launch an EC2 instance in our subnet.

Let’s head over to the EC2 dashboard by clicking and typing EC2 into the search bar at the top.

Click on instances on the left side — launch instance on the right.

Our flavor of choice:

![alt text](/assets/vpc9.webp)

![alt text](/assets/vpc10.webp)

Download the key pair then launch instances.

Select our instance and click on connect at the top.

That will lead us here:


![alt text](/assets/vpc11.webp)

Click connect again and we are ready to type whichever cmd you like.

![alt text](/assets/vpc12.webp)