Web Infrastructure Design
Task 1: Definitions and Explanations

1. Reasons for adding additional elements:
The goal of adding additional elements is to improve the overall reliability, scalability, and performance of the web infrastructure. Specifically:
- Adding a new server allows for the implementation of a load balancer, which can distribute incoming traffic across multiple servers, preventing a single point of failure.
- The load balancer helps handle increased traffic volumes and ensures better load distribution, improving the overall user experience.

2. Load Balancer Distribution Algorithm:
The load balancer is configured to use the Round Robin algorithm. This algorithm distributes incoming requests sequentially to the available servers, one after another. The requests are served by the servers in a circular fashion, starting from the first server and moving to the next, unless a server is down. This algorithm works well when the servers are of equal specification and there are not many persistent connections.

3. Active-Active vs Active-Passive Setup:
The load balancer enables an Active-Active setup, where both server nodes are actively running the same service simultaneously. In contrast, an Active-Passive setup would have one node actively serving requests, while the other node is in a passive, standby mode. The key difference is in performance:
- Active-Active allows access to the resources of all servers during normal operation, providing better performance and scalability.
- Active-Passive has the backup server only becoming active during a failover event, which can result in longer downtime.

4. Database Primary-Replica (Master-Slave) Cluster:
The database setup uses a Primary-Replica (Master-Slave) cluster configuration. In this setup:
- The master database server logs all updates, which are then replicated to the slave servers.
- This enables the spread of read access across multiple servers, improving scalability.
- It also provides redundancy and failover capabilities, as the slaves can take over if the master becomes unavailable.
- The replication can be synchronous or asynchronous, depending on the requirements.

5. Difference between Primary and Replica Nodes:
- The primary node is the main, authoritative source of the application codebase and data.
- The replica nodes are copies of the primary node, providing redundant instances of the application.
- Replica nodes help protect against hardware failures and increase the capacity to serve read-heavy requests (e.g., retrieving documents).

Issues:
A. Single Point of Failure (SPOF):
The major SPOF in this infrastructure is having only one load balancer. If the load balancer fails, the entire system will be down, as there is no redundancy or failover mechanism.

B. Security Issues:
- The lack of HTTPS encryption means that the communication between the application and users is not secure, exposing sensitive information to potential eavesdroppers.
- The absence of a firewall leaves the system vulnerable to various attacks, such as denial-of-service (DoS) or data breaches.

C. Lack of Monitoring:
Without any monitoring in place, it becomes difficult to identify and address issues proactively. Monitoring is essential for understanding system performance, detecting problems, and improving the overall user experience.