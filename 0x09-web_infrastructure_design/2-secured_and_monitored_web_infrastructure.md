**Specifics:**

- **Firewalls:** Three firewalls are added to enhance security. They help protect the infrastructure by enforcing security rules and filtering incoming and outgoing traffic, thus reducing the risk of unauthorized access and attacks.

- **SSL Certificate (HTTPS):** Serving traffic over HTTPS is essential for encrypting data in transit between clients and servers. It ensures data confidentiality, integrity, and authenticity.

- **Monitoring:** Monitoring tools (SumoLogic or other monitoring services) are used to track the health and performance of the infrastructure, detect issues proactively, and provide insights for troubleshooting and optimization.

- **How Monitoring Collects Data:** Monitoring clients are deployed on each server, collecting data on system performance, resource usage, application logs, and other metrics. This data is sent to the monitoring service for analysis and reporting.

- **Monitoring Web Server QPS:** To monitor web server QPS (Queries Per Second), you can set up custom monitoring scripts or use existing monitoring tools to collect and analyze request logs, measuring the rate of incoming HTTP requests.

**Issues with the Infrastructure:**

1. **Terminating SSL at the Load Balancer Level:** Terminating SSL at the load balancer can be an issue if not properly secured because the data between the load balancer and the web servers would be unencrypted. It's important to ensure that the communication between the load balancer and web servers is secure.

2. **Single MySQL Server Capable of Accepting Writes:** If there's only one MySQL server capable of accepting writes, it becomes a single point of failure for write operations. Implementing a primary-replica MySQL cluster as described helps with redundancy and high availability.

3. **Servers with All the Same Components:** Having identical components on all servers can be problematic because it limits the flexibility to scale or optimize specific components as needed. It may not be efficient in terms of resource utilization. Diversifying server roles, for example, separating database servers from application servers, can be more efficient and scalable.
