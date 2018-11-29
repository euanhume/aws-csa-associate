# High Availability 

## Elastic Load Balancing (ELB) Essentials

+ Load Balancing (as a concept) is a common method used for distributing traffic across servers
+ An Elastic Load Balancer is an EC2 service that automates the process of distributing incoming traffic (evenly) to all instances that are assoicated with the ELB. 
+ Cross-zone load balanacing 
  + An elastic load balancer can load balance traffic to instances located across multiple availability zones
  + This allows for highly availability and fault tolerant architecture
+ Elastic load balancing can be paired with Auto Scaling to enhance high availability and fault tolerance, AND allow for automated scalability and elasticity
+ An ELB has it's own DNS record set that allows for direct access from the open internet

Other Important ELB facts: 

+ An ELB can be public-facing or used as an internal load balancer and load balance to internal EC2 instances on private subnets (as often done with multi-tier applications)
+ ELBs will automatically stop serving traffic to an instance that becomes unhealthy (via health checks)
+ An ELB or ALB can help reduce compute power on an EC2 instance by allowing for an SSL certificate to be applied directly to the elastic load balancer 

## Classic Elastic Load Balancer

+ A "classic" elastic laod balancer is designed for simple balancing of traffic to multiple EC2 instances 
+ There are no granular routing "rules" - all instances get routed to evenly, and no special routing request can be made based on specific content requested from the user 
+ TCP, SSL, HTTP, HTTPS

## Application ELB

+ An application Load Balancer is designed for balancing of traffic to one or more instance target groups using content-based "rules"
+ Content-based rules (setup on the listener) can be configured using: 
  + Host-based rules: 