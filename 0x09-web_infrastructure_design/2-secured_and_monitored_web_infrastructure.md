Web Infrastructure Design
Task 2: Definitions and Explanations

1. Reasons for Adding New Components:
- Firewalls for each server to protect them from being attacked and exploited
- 1 SSL certificate to serve www.foobar.com over HTTPS
- 3 monitoring clients that will collect logs and send them to the data collector, Sumo Logic

2. Purpose of Firewalls:
Firewalls are a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. They establish a barrier between a trusted network and an untrusted network.

3. Importance of HTTPS:
The traffic is now served over HTTPS, which encrypts the data using Transport Layer Security (TLS). This is a more secure approach compared to the previous HTTP protocol, which transmitted data in plain text.

4. Purpose of Monitoring:
Monitoring provides the capability to detect and diagnose any web application performance issues proactively.

5. How Monitoring Tool Collects Data:
The monitoring tool collects logs from the application server, MySQL database, and Nginx web server. Logs are automatically produced and time-stamped documentation of events relevant to a particular system.

6. Monitoring Web Server QPS:
If you want to monitor the web server's queries per second (QPS), you would monitor it from both the network and application levels, as one web server handles 1K queries per second.

Issues:
A. SSL Termination at Load Balancer Level:
Terminating SSL at the load balancer level is an issue because decryption is resource and CPU-intensive. Placing the decryption burden on the load balancer enables the server to spend processing power on application tasks, but this may still be a potential issue.

B. Single MySQL Server for Writes:
Having only one MySQL server capable of accepting writes is an issue because if it goes down, no data can be added or updated, meaning some features of the application won't work.

C. Identical Server Components:
Having servers with all the same components (database, web server, and application server) might be a problem because if there is a bug in one of the components in one of the servers, the bug will be present in the other servers as well.