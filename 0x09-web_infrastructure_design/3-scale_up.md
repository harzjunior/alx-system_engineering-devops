# Readme: Application Server vs. Web Server

In this readme, we'll discuss the distinctions between an application server and a web server in a typical web application infrastructure. We'll also outline the components added to meet the requirements, explaining their roles and importance in the infrastructure.

## Application Server vs. Web Server:

### Web Server:
A web server is a software or hardware component responsible for handling HTTP requests and serving static content like HTML, CSS, JavaScript, and media files (e.g., images, videos). The primary role of a web server is to receive incoming HTTP requests from clients (typically web browsers) and respond with the requested files. Common web server software includes Nginx, Apache, and Microsoft Internet Information Services (IIS).

**Why Web Server:**
A web server is added to serve static content efficiently and handle initial client requests. It simplifies the process of serving static files and can also act as a reverse proxy for forwarding dynamic requests to the application server.

### Application Server:
An application server is responsible for executing application-specific logic, processing dynamic requests, and generating dynamic content. It communicates with the database to retrieve and manipulate data, runs business logic, and generates HTML or other data to be served to clients. Application servers often use technologies like Ruby on Rails, Django, Node.js, or ASP.NET.

**Why Application Server:**
An application server is crucial for executing the core business logic of a web application. It handles dynamic content generation and database interactions. By separating this logic from the web server, you achieve a more modular and maintainable system.

## Infrastructure Components:

### 1. Server:
A dedicated server, whether physical or virtual, is added to host and manage various components of the web application. This server acts as the foundation for the infrastructure.

**Why Server:**
A server is essential to provide the computational resources needed for running the web and application servers, ensuring the web application's performance and availability.

### 2. Load-Balancer (HAproxy):
Load balancers, like HAproxy, distribute incoming network traffic across multiple servers to ensure even distribution and efficient utilization of resources. In this case, we have two load balancers configured as a cluster to enhance redundancy and fault tolerance.

**Why Load-Balancer:**
Load balancers are added to improve the scalability, fault tolerance, and reliability of the infrastructure. By distributing incoming traffic, they prevent overloading any single server and enable high availability.

### 3. Split Components:
Each component of the web application (web server, application server, and database) is hosted on separate servers. This separation is beneficial for several reasons:

- **Scalability:** It allows individual components to be scaled independently. For example, if the application server experiences increased load, you can add more application server instances without affecting the web server or database.

- **Resource Optimization:** Different components have different resource requirements. Separating them allows you to allocate resources according to their specific needs.

- **Modularity:** Separation promotes a modular and maintainable architecture. Each component can be developed, tested, and updated independently, making the application more manageable.

**Why Split Components:**
Splitting components into separate servers improves scalability, resource allocation, and maintainability. It's a best practice for designing robust web application infrastructures.

In summary, the addition of these components - web server, application server, server, load balancer, and splitting components onto separate servers - is essential to create a well-structured, scalable, and reliable web application infrastructure that can efficiently serve user requests and handle dynamic content generation.
