# Databases

## DynamoDB Essentials

+ DynamoDB is a fully-managed NoSQL database service provided by AWS
+ It is similar to MongoDB, but is a home-grown AWS solution
+ Is schema-less, and uses a key-vaule store 
+ You specify the required throughput capacity and DynamoDB, being fully-managed, doe the rest. 

+ Deing fully-managed means 
  + Service manages all provisioning (and scaling) of underlying hardware
  + Fully distrubted, and scales automatically with demand and growth
  + Built as a fault tolerant highly available service: 
    + Fully synchronizes, on the back end, the data across all of the availability zones within the region you created the DynamoDB tables in

+ DynamoDB also easily integrates with other AWS services, such as Elastic MapReduce 
  + Can easily move data to a hadoop cluster in Elastic MapReduce 

+ Popular use cases include: 
  + IOT: Storing meta data
  + Gaming: Storing session information, leaderboards
  + Mobile: Storing user profiles, personalization 
