# VPC 

## Route Tables

"A route table contains a set of rules, called routes, that are used to determine where network traffic is directed" - Amazon web services

+ A route table's rules are comprised of two main components: 
  + Destination: The CIDR block range of the target (where the data is routed to)
  + Target: A name identifier of where the data is being routed to

+ By default, all subnets traffic is allowed to each other available subnet within your VPC which is called the local route 
+ You cannot modify the local route

+ Unlike an IGW, you can have multiple "active" route tables in a VPC
+ You cannot delete a route table if it has "dependancies" (associated subnets)

Best practice is to leave the default route table nd create a new route table when new routes are needed for specific subnets

Note: The "default" VPC already has a "main" route table 

| Destination   | Target        |
| ------------- |:-------------:|
| 172.31.0.0/16 | local         | 
| 0.0.0.0/0     | igw-95d589f2  |
