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
