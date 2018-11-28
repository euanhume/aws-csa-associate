# VPC

## Virtual Private Cloud (VPC) Essentials 

"Amazon Virtual Private Cloud (Amazon VPC) enables you to launch Amazon Wed Services (AWS) resources into a virtual network that you've defined. This virtual network closely resembles a traditional network that you'd operate in your own datacenter, with the benefits of using the scalable infrastructure of AWS" - Amazon Web Services

A VPC is designed ot resemble: 
+ Private on-premise data centers
+ Private corporate network

Private network features available in AWS VPCs: 
+ Private and Public subnets
+ Scalable architecture 
+ Ability to extend corporate/on-premise network to the cloud as if it was part of your network (VPN)

Important VPC Facts: 
+ A VPC is hosted within a chosen AWS region 
+ A VPC spans multiple availability zones within a region 
  + This allows you to provision redundant resources in seperate availability zones while having them accessible on the same network (foundation of high availability and fault tolerant architecture)
+ AWS provides a DNS server for your VPC so each instance has a hostname. However, you can run your own DNS servers by changing the DHCP option set configuration within the VPC. 

## Benefits of a Virtual Private Cloud (VPC)

+ Ability to launch instances into a subnet
+ Ability to define custome CIDR (IP address range) inside each subnet
+ Ability to configure routes between subnets via route tables
+ Ability to configure an internet gateway to provide a route to the internet for resources launched inside the VPC
+ Ability to create a layered network of resources
+ Ability to extend your on-premise network into the cloud with VPN/VPG and an IPsec VPN tunnel 
+ Layered Security 
  + Instance level Security Groups (firewall on the instance level)
  + Subnet level network ACLs (firewall on the subnet level)

## Default VPC 

+ The default VPC is the VPC that comes preconfigured in your AWS account when it is first created 
+ The default VPC has a different setup than a non-default VPC
+ The default VPC is meant to allow the user easy access to a VPC without having to configure it from scratch
+ In the default VPC, all subnets have a route to the internet via a route table and an attached IGW
+ Each instance launched in the default VPC (by default) has a private and public IP address (defined on the subnet settings)

## VPC Limits

+ 5 VPCs per region (more available upon request)
+ 5 interney gateways per region (this is equal to your VPC limit because you can only have one internet gateway attached to a VPC at a time)
+ 50 customer gateways per region
+ 50 VPN connections per region
+ 200 route tables per region / 50 entries per route table
+ 5 elastic IP addresses
+ 500 security groups per VPC
+ 50 rules per security group 
+ 5 security groups per netowrk interface (security groups although generally referred to as being on the on instance level are technically on the VPC level)

## VPC IP addressing

+ IPv4 
  + Public and Private Addresses
  + 32 Bits 4-8bit octects 128.0.200.1

+ IPv6
  + Public Only
  + 128 Bits 8 - 4chr hexadecimal 2001:0000:0eab:DEAD:0000:00A0:ADCD:004E

## CIDR Notation (IPv4)

+ 10.0.0.0/16 is 10.0.0.0 to 10.0.255.255 which is 65,536 addresses
+ 10.0.0.0/24 is 10.0.0.0 to 10.0.0.255 which is 256 addresses
+ 10.0.0.0/32 is 10.0.0.0 to 10.0.0.0 which is 1 addresses
+ 0.0.0.0/16 is 0.0.0.0 to 255.255.255.255 which is the entire internet 

## VPC Endpoints

+ Gateway Endpoints 
  + Amazon S3
  + Amazon DynamoDB
+ Interface Endpoints
  + CloudWatch Logs, CloudBuild, KMS, Kinesis, Service Catalog 
