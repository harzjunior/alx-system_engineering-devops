**1. Why the Additions:**

- **Two Servers:** The addition of two servers provides redundancy and helps eliminate the single point of failure (SPOF) in the original infrastructure.

- **Load Balancer (HAproxy):** A load balancer is added to distribute incoming traffic evenly across multiple application servers, improving the performance and availability of the application.

- **Primary-Replica Database Cluster:** Implementing a MySQL Primary-Replica cluster ensures data redundancy and high availability, enhancing the database's reliability.

- **Security Issues:** Adding a firewall and enabling HTTPS is crucial to enhance security and protect the application and data from threats and unauthorized access.

- **Monitoring:** Implementing monitoring solutions is essential to track the health and performance of the infrastructure components and detect issues proactively.

**2. Load Balancer Distribution Algorithm:**
The load balancer (HAproxy) can be configured with various distribution algorithms. A common one is Round Robin, which evenly distributes requests in a circular manner to each available application server. This ensures a fair distribution of traffic. Other algorithms, such as Least Connections or IP Hash, can be used depending on specific requirements.

**3. Active-Active vs. Active-Passive Setup:**

- **Active-Active Setup:** In an Active-Active setup, both application servers are actively serving traffic simultaneously. The load balancer evenly distributes incoming requests to both servers. This configuration is used to increase application performance and redundancy.

- **Active-Passive Setup:** In an Active-Passive setup, one application server is active and serving traffic, while the other server is in standby mode. The load balancer sends all traffic to the active server. The passive server becomes active only if the primary server fails. This setup enhances redundancy but may underutilize resources.

**4. How a Database Primary-Replica (Master-Slave) Cluster Works:**

In a Primary-Replica (or Master-Slave) database cluster:

- **Primary Node:** This is the primary database server responsible for handling write operations (INSERT, UPDATE, DELETE) and read operations. All data changes happen on the primary node, which replicates these changes to the replica nodes.

- **Replica Node:** The replica nodes are read-only copies of the data on the primary node. They replicate data from the primary node and serve read requests. This offloads read traffic from the primary node and provides data redundancy.

**5. Difference Between Primary and Replica in Regard to the Application:**

- **Primary Node:** The primary database server is responsible for processing write operations, which update and change the data. The application typically connects to the primary node for data modification, ensuring data consistency.

- **Replica Node:** Replica nodes are used to serve read operations (SELECT queries) from the application. This offloads the primary node, improving read performance and scalability. However, the data on the replica nodes may slightly lag behind the primary node due to replication delays.

**Issues with the Expanded Infrastructure:**

**1. Single Point of Failure (SPOF):**
The infrastructure still has a potential SPOF in the load balancer. If the load balancer fails, incoming traffic won't be distributed correctly. Implementing redundancy for the load balancer is essential.

**2. Security Issues:**
- There's no mention of a firewall, which exposes the infrastructure to potential security threats. Adding a firewall is crucial for controlling incoming and outgoing traffic.
- The absence of HTTPS leaves data transmitted between clients and servers vulnerable to interception. Implementing HTTPS encryption is essential for security.

**3. No Monitoring:**
The infrastructure lacks monitoring, which is essential for detecting issues, performance bottlenecks, and security breaches. Implementing monitoring tools and practices is crucial for proactive issue identification and resolution.
