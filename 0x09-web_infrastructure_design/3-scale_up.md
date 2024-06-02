Web Infrastructure Design
Task 3: Definitions and Explanations

1. Reasons for Adding New Components:
- 1 additional server: This allows separating each component (web server, application server, and database) into their own dedicated servers. It also adds an extra server with all the components to serve as a backup in case any component or server fails. Each server is being monitored and has a firewall.
- 1 additional load balancer: This extra load balancer will assist in handling more traffic across the whole infrastructure.