create a user service crud application using golang with the below specifications 

Transport Layer 
gRPC + Rest (use grpc-gateway)

Database Layer 
Cassandra or any wide table database like (scylladb, astradb, cosmosdb)

Operations Supported 
1. Create User
2. Update User
3. Block User
4. Unblock User
5. Update user phone number, email
6. Get user by phone number or email

Assume the following properties for user

1. first name 
2. last name
3. gender
4. date of birth
5. phone number 
6. email

Good to haves 
1. Unit tests 
2. Integration tests with some benchmarks around reqs/s and memory, cpu utilization in local
