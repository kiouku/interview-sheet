# System Design

Three things to consider:

- What are the different architectural pieces that can be used?
- How do these pieces work with each other?
- How can we best utilize these pieces: what are the right tradeoffs?

# Key Characteristics of Distributed Systems

## Scalability  
Scalability is the capability of a system, process, or a network to grow and manage increased demand. 

- Horizontal scaling: means that you scale by adding more servers into your pool of resources whereas 
- Vertical scaling: means that you scale by adding more power (CPU, RAM, Storage, etc.) to an existing server. It implies downtime.

## Reliability
Reliability is the probability a system will fail in a given period. In simple terms, a distributed system is considered reliable if it keeps delivering its services even when one or several of its software or hardware components fail. Any failing machine can always be replaced by another healthy one, ensuring the completion of the requested task.

## Availability
Availability is the time a system remains operational to perform its required function in a specific period. It is a simple measure of the percentage of time 
that a system, service, or a machine remains operational under normal conditions. 

## Efficiency
Two standard measures of its efficiency are the response time (or latency) that denotes the delay to obtain the first item and the throughput (or bandwidth) 
which denotes the number of items delivered in a given time unit (e.g., a second). The two measures correspond to the following unit costs:

Number of messages globally sent by the nodes of the system regardless of the message size.
Size of messages representing the volume of data exchanges.

## Serviceability or Manageability
Serviceability or manageability is the simplicity and speed with which a system can be repaired or maintained; if the time to fix a failed system increases, then availability will decrease. 
Early detection of faults can decrease or avoid system downtime. 

# Load Balancing
It helps to spread the traffic across a cluster of servers to improve responsiveness and availability of applications, websites or databases. LB also keeps track of the status of all the resources while distributing requests. If a server is not available to take new requests or is not responding or has elevated error rate, LB will stop sending traffic to such a server.

Load balancers consider two factors before forwarding a request to a backend server. They will first ensure that the server they choose is actually responding appropriately to requests and then use a pre-configured algorithm to select one from the set of healthy servers. We will discuss these algorithms shortly. Example of algorithm: Least Connection Method.

## Benefits
- Users experience faster, uninterrupted service. Users won’t have to wait for a single struggling server to finish its previous tasks. Instead, their requests are immediately passed on to a more readily available resource.
- Service providers experience less downtime and higher throughput. Even a full server failure won’t affect the end user experience as the load balancer will simply route around it to a healthy server.
- Load balancing makes it easier for system administrators to handle incoming requests while decreasing wait time for users.
- Smart load balancers provide benefits like predictive analytics that determine traffic bottlenecks before they happen.
- System administrators experience fewer failed or stressed components. Instead of a single device performing a lot of work, load balancing has several devices perform a little bit of work.

# Caching
 Caches take advantage of the locality of reference principle: recently requested data is likely to be requested again. A cache is like short-term memory: it has a limited amount of space, but is typically faster than the original data source and contains the most recently accessed items. Caches can exist at all levels in architecture, but are often found at the level nearest to the front end where they are implemented to return data quickly without taxing downstream levels.

# Database Indexes
Simply saying, an index is a data structure that can be perceived as a table of contents that points us to the location where actual data lives. So when we create an index on a column of a table, we store that column and a pointer to the whole row in the index.

An index can dramatically speed up data retrieval but may itself be large due to the additional keys, which slow down data insertion & update. When adding rows or making updates to existing rows for a table with an active index, we not only have to write the data but also have to update the index. 

# Proxies

# Redundancy and Replication

Redundancy is the duplication of critical components or functions of a system with the intention of increasing the reliability of the system, usually in the form of a backup or fail-safe, or to improve actual system performance. For example, if there is only one copy of a file stored on a single server, then losing that server means losing the file. Since losing data is seldom a good thing, we can create duplicate or redundant copies of the file to solve this problem.

Redundancy plays a key role in removing the single points of failure in the system and provides backups if needed in a crisis. For example, if we have two instances of a service running in production and one fails, the system can failover to the other one.

Replication means sharing information to ensure consistency between redundant resources, such as software or hardware components, to improve reliability, fault-tolerance, or accessibility.

Replication is widely used in many database management systems (DBMS), usually with a master-slave relationship between the original and the copies. The master gets all the updates, which then ripple through to the slaves. Each slave outputs a message stating that it has received the update successfully, thus allowing the sending of subsequent updates.

# SQL vs. NoSQL

## SQL 
Relational databases store data in rows and columns. Each row contains all the information about one entity and each column contains all the 
separate data points. Relational databases are structured and have predefined schemas.

### ACID
- Atomicity: guarantees that each transaction is treated as a single "unit", which either succeeds completely, or fails completely.
- Consistency: ensures that a transaction can only bring the database from one valid state to another, maintaining database invariants: any data written to the database must be valid according to all defined rules, including constraints, cascades, triggers, and any combination thereof.
- Isolation: ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially.
- Durability: guarantees that once a transaction has been committed, it will remain committed even in the case of a system failure (e.g., power outage or crash)

Some examples: mySQL, postgres... 

## NoSQL
- Key-Value Stores: Data is stored in an array of key-value pairs. Well-known key-value stores include Redis and DynamoDB.

- Document Databases: In these databases, data is stored in documents (instead of rows and columns in a table) and these documents 
are grouped together in collections. Each document can have an entirely different structure. Document databases include the CouchDB and MongoDB.

- Wide-Column Databases: Instead of ‘tables,’ in columnar databases we have column families, which are containers for rows. 
Unlike relational databases, we don’t need to know all the columns up front and each row doesn’t have to have the same number of columns. 
Columnar databases are best suited for analyzing large datasets - big names include Cassandra and HBase.

- Graph Databases: These databases are used to store data whose relations are best represented in a graph. 
Data is saved in graph structures with nodes (entities), properties (information about the entities), and lines (connections between the entities). 
Examples of graph database include Neo4J and InfiniteGraph.

## Tradeoffs
Here are a few reasons to choose a SQL database:

- We need to ensure ACID compliance. ACID compliance reduces anomalies and protects the integrity of your database by prescribing exactly how transactions interact 
with the database. Generally, NoSQL databases sacrifice ACID compliance for scalability and processing speed, but for many e-commerce and financial applications, 
an ACID-compliant database remains the preferred option.
- Your data is structured and unchanging. If your business is not experiencing massive growth that would require more servers and if you’re only working with data that is consistent, then there may be no reason to use a system designed to support a variety of data types and high traffic volume.

A few popular examples of NoSQL databases are MongoDB, CouchDB, Cassandra, and HBase.

- Storing large volumes of data that often have little to no structure.
- Making the most of cloud computing and storage. Cloud-based storage is an excellent cost-saving solution but requires data to be easily spread across multiple servers to scale up. Using commodity (affordable, smaller) hardware on-site or in the cloud saves you the hassle of additional software and NoSQL databases like Cassandra are designed to be scaled across multiple data centers out of the box, without a lot of headaches.
- Rapid development. NoSQL is extremely useful for rapid development as it doesn’t need to be prepped ahead of time. 

# Data partitioning

# CAP Theorem

The CAP Theorem is a fundamental theorem in distributed systems that states any distributed system can have at most two of the following three properties.

- Consistency: All nodes see the same data at the same time. Consistency is achieved by updating several nodes before allowing further reads.
- Availability: Every request gets a response on success/failure. Availability is achieved by replicating the data across different servers.
- Partition tolerance: The system continues to work despite message loss or partial failure. A system that is partition-tolerant can sustain any amount of network failure that doesn’t result in a failure of the entire network. Data is sufficiently replicated across combinations of nodes and networks to keep the system up through intermittent outages.

The CAP theorem applies to distributed systems that store state. The CAP theorem states that a distributed system cannot simultaneously be consistent, available, and partition tolerant. 

Because, to be consistent, all nodes should see the same set of updates in the same order. But if the network suffers a partition, updates in one partition might not make it to the other partitions before a client reads from the out-of-date partition after having read from the up-to-date one. The only thing that can be done to cope with this possibility is to stop serving requests from the out-of-date partition, but then the service is no longer 100% available.

# Consistency patterns
With multiple copies of the same data, we are faced with options on how to synchronize them so clients have a consistent view of the data. Recall the definition of consistency from the CAP theorem - Every read receives the most recent write or an error.

## Weak consistency
After a write, reads may or may not see it. A best effort approach is taken.

This approach is seen in systems such as memcached. Weak consistency works well in real time use cases such as VoIP, video chat, and realtime multiplayer games. For example, if you are on a phone call and lose reception for a few seconds, when you regain connection you do not hear what was spoken during connection loss.

## Eventual consistency
After a write, reads will eventually see it (typically within milliseconds). Data is replicated asynchronously.

This approach is seen in systems such as DNS and email. Eventual consistency works well in highly available systems.

## Strong consistency
After a write, reads will see it. Data is replicated synchronously.

This approach is seen in file systems and RDBMSes. Strong consistency works well in systems that need transactions.

# Availability patterns
There are two main patterns to support high availability: fail-over and replication.

## Fail-over
### Active-passive
With active-passive fail-over, heartbeats are sent between the active and the passive server on standby. If the heartbeat is interrupted, the passive server takes over the active's IP address and resumes service.

The length of downtime is determined by whether the passive server is already running in 'hot' standby or whether it needs to start up from 'cold' standby. Only the active server handles traffic.

Active-passive failover can also be referred to as master-slave failover.

### Active-active
In active-active, both servers are managing traffic, spreading the load between them.

If the servers are public-facing, the DNS would need to know about the public IPs of both servers. If the servers are internal-facing, application logic would need to know about both servers.

Active-active failover can also be referred to as master-master failover.

### Disadvantage(s): failover
Fail-over adds more hardware and additional complexity.
There is a potential for loss of data if the active system fails before any newly written data can be replicated to the passive.

# Consistent Hashing

Distributed Hash Table (DHT) is one of the fundamental components used in distributed scalable systems. Hash Tables need a key, a value, and a hash function where hash function maps the key to a location where the value is stored.

Consistent hashing allows us to distribute data across a cluster in such a way that will minimize reorganization when nodes are added or removed. Hence, the caching system will be easier to scale up or scale down.

In Consistent Hashing, when the hash table is resized (e.g. a new cache host is added to the system), only ‘k/n’ keys need to be remapped where ‘k’ is the total number of keys and ‘n’ is the total number of servers. Recall that in a caching system using the ‘mod’ as the hash function, all keys need to be remapped.

In Consistent Hashing, objects are mapped to the same host if possible. When a host is removed from the system, the objects on that host are shared by other hosts; when a new host is added, it takes its share from a few hosts without touching other’s shares.

Here’s how consistent hashing works:

1 - Given a list of cache servers, hash them to integers in the range. To map a key to a server,
2 - Hash it to a single integer.
3 - Move clockwise on the ring until finding the first cache it encounters. That cache is the one that contains the key. 

# Long-Polling vs WebSockets vs Server-Sent Events

# REST

## Definition
REST is a software design pattern typically used for web applications. It stands for REpresentational State Transfer. The basic idea of REST is treating objects on the server-side (as in rows in a database table) as resources than can be created or destroyed.

The most basic way of thinking about REST is as a way of formatting the URLs of your web applications. For example, if your resource was called "posts", then:

/posts Would be how a user would access ALL the posts, for displaying.

/posts/:id Would be how a user would access and view an individual post, retrieved based on their unique id.

/posts/new Would be how you would display a form for creating a new post.
 
## Fundamental REST principles 

- Client-Server Communication: Client-server architectures have a very distinct separation of concerns. All applications built in the RESTful style must also be client-server in principle.

- Stateless: Each client request to the server requires that its state be fully represented. The server must be able to completely understand the client request without using any server context or server session state. It follows that all state must be kept on the client. We will discuss stateless representation in more detail later.

- Cacheable: Cache constraints may be used, thus enabling response data to to be marked as cacheable or not-cachable. Any data marked as cacheable may be reused as the response to the same subsequent request.

- Uniform Interface: All components must interact through a single uniform interface. The interface is the same! This also means that implementation changes can be made in isolation. Such changes, will not affect fundamental component interaction because the uniform interface is always unchanged. One disadvantage is that you are stuck with the interface. If an optimization could be provided to a specific service by changing the interface, you are out of luck. 

By REST you use the classical interface concept to decouple the client from the implementation of the REST service. In order to do define such an interface (contract between the client and the service) you have to use standards. This is because if you want an internet size network of REST services, you have to enforce global concepts, like standards to make them understand each other.)

# RESTful 
It is typically used to refer to web services implementing such an architecture.


# References
https://www.educative.io/courses/grokking-the-system-design-interview/3jEwl04BL7Q
https://dzone.com/articles/understanding-the-cap-theorem

