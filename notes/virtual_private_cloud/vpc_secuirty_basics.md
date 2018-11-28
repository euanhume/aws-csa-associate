# VPC 

## Network Access Control List (ACLs) Essentials

+ ACLs operate at the network/subnet level
+ They support allow and deny rules for traffic travelling into or out of a subnet
+ They are stateless: so return traffic must be allowed through an outbound rule 

+ They process rules in number order when decidin whether to allow traffic
+ Rules are evaluated in order, starting with the lowest rule number - for example:
  + If traffic is denied at a lower level number and allowed at a higher rule number, the allow rule will be ignored and the traffic will be denied  
+ The last rule in every ACL is a "catch all" deny rule
  + This means that unless a protocol/port is explicitly allowed, it will be denied

+ A network access control list (NACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one of more subnets

+ Best practice to increment numbers by 10 so if you have to place a rule in a certain order it does not create an issue

## Network Access Control List (ACLs) Rules

+ Rules are evaluated from lowest to highest based on "rule #"
+ The furst rule found that applies to the traffic type is immediately applied, regardless of any rules that come after it (have a higher "rule #")
+ A subnet can only be associated with ONE NACL at a time 
+ An NACL allows or denies traffic from entering a subnet. Once inside the subnet, other AWS resources (i.e. EC2 instances) may have an additional layer of security (security groups)

## Security Groups