
# systemdesignlearn
## CLient and Server Model 
- client:
    - A machine or process that request data or service from a server
    - note that a single machine a piece of sofrware can be both  a client and a server at the same tim. for instance,a single machine could act as a server  for end users and as a client for database
- Server:
    - A machine or proceess that provides data or service for client , usually by listening for incoming networki calls 
- Client -Server Model:
    - the paradigm by which modern systems asre designed , which consists of clients requesting data or service from servers and servers providing data or serviceto clients
- Ip Address
   - An adress given to each machine conneted to public internet. IPv4 addresses consist of four numbers separated by dots: a.b.c.d where allfournumbers are between 0 and 255. speacial values include:
   - 127.0.0.1: your own local machine. also refered to as Localhost
   - 192.168.x.y: your private network. for instance, your machine and allmachines on your private widi network will usually have the 192.168.* prefix 
- Port
    - Inorder for multiple programs to listen for new network connections on the same machine without colliding, they pich a port to liste on. On port iis an innteger between 0 and 65535 (2^16 ports total)
    - typically ports 0-1023 aree reserved for system ports- well-known ports and shouldnt be used by user-level processes.Certain ports havepre-defined uses, adn although you ususlly wont  be required to have them  memorized, they can sometimes come in handy. Below are some examples:
        - 22: Secure Shell
        - 53: DNS lookup
        - 80: HTTP
        - 443: Https
- DNS
    - short for domain name system, it describes the entities and protocal involved in the translation from domain names to IP address. Typically, machines make a DNS query to a well known entity which is responsible for returning teh IP address( or multiple one) of the requested domain name in the response
- IP 
    - Internet Protocol, this network protocol outlines how almost all machine-to-machine communication should in the world. Other protocols like TCP, UDP adn HTTP are built on top of IP
- TCP
    - network protocol built on top of the inteenet Prrotocol. Allows for orderd  reliable data delivery between machines over the  public internet by creating a connection 
    - TCP is ususlly implemented in kenel, which exposes sockets to application that they can use to steam data through an open connection
- HT
    - the hypertext TRanfer protocol is a very commmon network protocol implemented on top of TCP. clients make HTTP requests. servers repond with a response
    - ![tcp](https://user-images.githubusercontent.com/22860697/124317352-e3642580-db2b-11eb-9113-587ca97ffa5b.JPG)
- IP packet
    - someytimes more broadly referred to as just a network packet, an IP packet is effectively the smalllest unit used to describe data beingsent ove IP, aside form bytes. AN IP packet consist of:
        - an IP header, which contains teh source and destination IP addresses as well ass other information related to the network
        - a payload, which is just the data being sent over the network
# client and Servers
- key terms; Client Server client - server model,IP Address, Port ,DNS
# network protocals 
 - IP packets TCP header HTTPS request, As Dauting as they may seem these low level networking concepting are essential to understanding how machine in a system communicate with one another. And as we all know, proper communication is key for thriving relationships
 - Key term : IP, TCP, HTTP, IP Packet
# Storage 
- get data and store data
- curl send and get data from the server
- Database 
- Disk 
- Memory
- Persistent Storage
# Latency and Throughput
- Latency: the time is takes for a certain operation in a system. Most Often this measure is time duration like milliseconds or seconds. 
     - Hierarchy: read or tranfer 1MB : RAM (.25ms) SSD (1ms) Network (10ms) HDD (20ms) Inter-continetal Round Trip(150ms)
- Throughput: the number of operations that a system can handle properly per time unit. For intance the through put of a server can offen be measured in request per second (RPS or QRS)
# Availability
- Process
- Server
- Node/Instance/Host
- Redundancy : one example is LBS,  passive(airplane engine) and Active (only one of the machine has main role)
- Nine
- SLA
- SLO
# Caching :
- can be done as Hardware or software
- can be between Client and Server and Database
- the ideal for caching is to reduce amount of network request
- boost up the computational, or data recently or frequently access
- reduce the overload rate
- ex: of a post web, store in database and caching , when edit it also overite the database and caching ,  write through caching 
- writeback caching , only cach will update and sometime in future will update data
- depend on type of data design the caching, such as comment or view count, 
- imutable data  or some other type
# Proxies : 
- Forward Proxy: A server sits between  a client and servers and acts on behalf of the client, Typically used to mask the clinet's identity (Ip address) Note that forward  proxies are often referred to as just proxies 
- hide identity of client from proxy
- Reverse Proxy: a Server that sit between clients and servers and ac on behalf of the servers, typically used for logging, load balancing, or caching
- filter out some request or logging system
- can act as a shield to distribute the request to server
# load balancer: 
- more request more change of failure
- LB help horiontal increase
- load balancer: A type of reverse proxy that distributes traffic across servers. LB can be found in many parts of a system, form the DNS layer all the way to the databases layer.
- Server-Selection Strategy: how a LB chooses servers when distributing traffic amongst multiple servers. Commonly used strategies include round-robin, random selection, performance metrics, like the fastest reponse time or the least amount of traffic), and IP-based routing.
- Hot Spot: when distributing a workload across a set of servers, that workload might be spread unevenly. this can happen if your sharding key or your hashing function are suboptimal, or if your workload is naturally skewed: some servers will receive a lot more traffic than other, thus creating a "hot spot"
- HW or SW LB
- round-robin: method go through all server in one order.
- IP base: hash the ip address of the client to distribute server for client, 
# Hashing: 
- Consistent Hashing: Type of hashing that miminizeds the number of key that need to be remapped when a hash table get ressized. it's often used by load balancer to distribute traffic to server; It minimizers the number of request that get forwarded to differebt servers are add or when existing servers are brought down
- Rendezvous Hashing : A type of hashing also coined highest random weight hashing. Allows  for minimal redistribution of mapping when a server goes down
- SHA- Secure hash ALgorithms, which is collection of cryptographic hash functions used in the industry, these days, SHA-3 is a popular choice to use in a system
# Relational databases: 
- database: record data and query data.they themselves servers that are long lived and  interact with the rest of your application through network calls, with protocols in tip of TCP or even HTTP. often save in disk
- DISK: HDD , SSD, non-volatile storage
- SQL
- ACID transaction
    - ATomicity : either all succeed or all fail
    - Consistency : the transaction cannot bring the database to an invalid state. rule stay the same after record
    - Isolation : the execution of multiple transactions concurrently will have the same effect as if they had been executed sequentially 
    - Durability : any committed transaction is written to non-volatile storage. it will not be undone by a crash, power loss, or network partition.
 - database index 
    - a special auxiliary data structure that allows your database to perform certain queried much faster. Indexes can typically only exist to reference structure data, like data stored in relational databases. create an index on one or multiple column in your databases to greatly speed up READ queries that you run very often. with the downside of slightly longer WRITE to your database, since writes have to also take place in the relevant index    
- Strong consistency
    - Strong COnsistency usually refer to the consistency of ACID transactions, as opposed to Eventual Consistency
- Eventual Consistency
    - A consistency model which is unlike Strong consistency. In this model, reads might return a view of the system that is stale. An eventually consistent datastore will give guarantees that the state of the database will eventually reflect writes within a time period
# key-Value Store ; 
- is a flexible NoSQL database that often used for caching and dynamic configuration. Popular options include DynamoDB, ETCD, Redis, adn ZooKeeper
# Specialized Storage Paradigms: 
- Blob storage: small and large scale system, allow the user to store and retrieve data based on the name if the blob. this is sort of like  akey value store but usualy blob stores have different guarantees. they might be slower than kv store but values can be megabytes large.Usually people user this to store things like Large binaries, Database snapshot, or images and other static assets that a website might have; blob storage is rathe complicated to have premise, and only giant companies like Google nad AMazon have infrastructure that supports it.so usually in the context of SYtem design interviews you can assume that you will be able to use GCS or S3. these are blob storage services hosted by Google and Amazonrespectively, that cost money depending on how much storage you use and how often you store and retrieve blobs form that storage.
- Time Series Database: a TSDB is a special kind of database optimized for storing and analyzing time-indexed data; data points that specifically occur at a given moment in time
- Graph Database: storing data following that graph data model. data entries in a graph database can have explicitly define relationships much like nodes in a graph can have edges; GD take advantage of their underlying graph structure to perform complex queries on deeply connected data very fast; GD are thus often preferred to relational databases when dealing with systems where data points naturally form a graph and have multiple levels of relationships. for example. social networks
- Cypher : a graph query language that was originally developed for Neo4j graph database ; Cypher queried are often  much simpler than their SQl counterparts. 
```code
    MATCH (some_node:SomeLabel)-[:SOME_RELATIONSHIP]-> (some_other_node:SomeLabel{some_property:'value'})
```
- Spatial Database: a type of database optimized for storing and querying spatial data like location on a map. Spatial databases rely on spatial indexes like quadtrees to quickly perform spatial queries like finding all locations in the vicinity of a region
- Quadtree
  - A tree data structure most commonly used to index two dimensional spatial data. Each node in a quadtree has either zero children nodes or exactly four children nodes.
  - typically , Quadtree nodes contain some form of spatial data-- for example, locations on a map-- with a maximum capacity of some specified number n. So long as nodes aren't at capacity, they remain leaf nodes; once they reach capacity, they're given four children nodes, and their data enties are split across the four children nodes 
  - A quadtree lend itself well to storing spatial data because it can be represented as a grid filled with rectangles that are recursively subdivided into four sub-rectangles, where each quadtree node is represented by a rectangle and each rectangle represents a spatial region.Assuming we're storing locations in the world, we can imagine a quadtree with a maximum node capacity n as follow: 
     - the root node, which representgs the entire world, is the outermost rectangle
     - if the entire world has more than n location, the outermost rectangle is divided into four quadrants,each representing a region of the wrld.
     - so long as a region has more than n locations, its corresponding rectangle is subdivided into four quadrants.
     - Regions that have fewer than n locations are undivided rectangles (leaf node)
     - the parts of the grid that have many subdivided rectangles represent densely populated areas(like cities). while the parts of the grid that have few subdivided rectangles represent sparsely populated areas
   - finding a given location in a perfect quadtree is an extremely fast operation that runs in log4(x) time (where x is the total number of locations), since quadtree nodes have four children nodes
# Replication And Sharding: 
 - Replication: 
 - Sharding: Data partitioning, base on a client's region, base on type of data being stored, base on hash of a column
 - Hot Spot: distributing a workload across a set of servers, that workload migh be spread unevenly. this can happen if your sharding key or your hashing  function are suboptimal, or if your workload is naturally skewed: so"me servers will receive a lot more traffic than others, thus creating a " hot spot"
#   Leader  Election:
- The Process by which nodes in cluster elect a so called leader amongst them, responsible for the primary operations of the service that these nodes support. When correctly implemented, leader election guarantees that all nodes in the cluster know which one is the leader at any given time and can elect a new leader if the leader dies for whatever reason.
- Consensus Algorithm: A type of complex algorithms used to have multiple entities agree agree on a single data value, like who the "leader" is amongst a group of machines. Two popular consensus  algorithms are Paxos and Raft
- Paxos and Raft: Two consensus algorithms that when implemented correctly, allow for the synchronization of certain operations, even in a distributed setting
- use in third party service - don't want to connect third party srvice direct, need middle man to do that 
- assume that this only have one service and it could be fail increase more service but how to ensure that no doublicate - is the leader comming to take the role of not dublicate, if current leader fail the other take place
- Zookeeper and Etcd help to implement the leader election
# peer to peer Network: 
 - collection of machines referred to as peers that divide a workload between themselves to presumably complete the workload faster than would otherwise be possible. Peer to Peer networks are often used in file-distribution systems
- Gossip Protocol: when a set of machines talk to each other in a un-coordinate manner in a cluster to spread information through a system without requiring a central source of data
# Polling and Streaming : 
- polling : the act of fetching a resource or piece of data regularly at an interval to make sure your data is not too stale
- streaming : in networking, it usually refers to the act of continuously getting a feed of information from a server by keeping an open connection between  the two machines or processes
# Configuration: 
- A set  of parameters or constants that are critical to a system. configuration is typically written in JSOn or YAML and can be either static,meaning  that its hard-coded in and shipped with your system's application code( like frontend code , for instance), or dynamic, meaning that it live outside if your system's application code
# Rate limiting: 
- the act of limiting the number of requests sent to or from or a system. rate limiting is most often used time limit the number of incoming requests in order to prevent DOS attacks and can be enforce at the IP address level, at the user account level , or at the region level, for example. Rate limiting can also be implementing in tiers. for instance, a type of network request could be limited to 1 per second, per 5s, per 10s, per 10 min.
- DOS attack: short for denial of service attack, a dos attack in which a malicious user tries to bring down or damage a system in order to render it unavailable to users. much of the time, it consists of flooding it with traffic. some Dos attacks are easily preventable with rate limiting, while others ca be far trickier to defend against.
- DDos attack: short for distribute DOS attack . a DDOS attack is a Dos attack with the traffic flooding the target system comes from many different sources (like a thousand of machines), making it much harder to defend against
- Redis service

# Logging and monitoring: 
- logging the act of collectung and storing logs-useful information about events in your systems. typically your programs will output log messages to iots STDOUT ir STDERR pipes, which will automatically get aggregated into a centralized logging solution
- monitoring: the process having visibility into a systems key metrics, monitoring is typically implemented by collecting important events in a system and aggregating them in human readable charts
- Alerting: the process through which system administrator get notified when critical system issues occur. Alerting can be set up by defining specific threaholds on monitoring chart, past which alerts are sent to communication channel like slack
# publish/Subscribe Pattern: 
- Often shorten as Pub/Sub, is a popular messaging model that consist of publisher adn subscribers. publishers publish massages to special topics without caring about or even knowing who will read those messages, and subscribe to topics and read message coming through those topic. Pub/Subs systems often come with very powerful guarantees like at least once delivery, persistent storage, ordering of messages and replay ability of messages
# Idempotent Operation: 
- A operation that has the same ultimate outcome regardless of how many times its performed . if an operation can be performed multiple times without changing its overall effect, its idempotent.Operations performed through a pub/sub messaging system typical have to be idempotent, since PUb/SUb systems tend to allow the same messages to be consumed multiple line
ex: increasing an integer value in a database is not an idempotent operation, since repeating this operation will not have the same effect as if it had been performed only once . Conversely, setting a value to "COMPLETE" is an idempotent operation, since repeating operation will always yield the same result: the value will be " COMPLETE"
- Cloud PUB/sub , Apache Kafka
# Map Reduce: 
- a popular framework for processing very large dataset in a distributed setting effiently, quickly, and in a fault-tolerant manner. A mapReduce job is comprised of 3 main steps: 
- the map step, which runs a map function on the various chunks of the dataset and transforms these chunks into intermediate key value pairs
- shuffle step, which reorganizes the intermediate key-value pairs such that pairs of the same key are routed to the same machine in the final step
- the reduce step, which runs a reduce function on the newly shuffled key value pairs and transforms them into  more meaningful data
# Distributed File System: 
- a Distributed File System is an abstraction over a usually large cluster of machines that allows them to act like one large file system. The two most popular implementations of DFS are the Google File System (GFS) and the Hadoop Distributed File System(HDFS).
- Typicallly DFSs take care of the classic availability and replication guarantees that can be tricky to obtain in a distributed-system setting.the overarching idea is that files are split into chunks of a certain size, and those chunksake sharded across a large cluster of machines. A central control plane is in charge of deciding where each chunk resides, routing reads to the right nodes, adn handling communication between machines
- Different DFS implementations have slightly different APIs and sematics but they achieve the same common goal: extremely large scale persistent storage.
# Man in middle attack :
- symmetric Encryption: a type of encryption that relies on only a single key to both encrypt and decrypt data. the  key must be known to all parties involved in communication and must therefore typically be shared betwwen the parties at one point or another; symmetric key algorithms tend to be faster than their asymmetric counterparts; the most widely used symmetric key algorithms are part of the advanced. ENcryption Standard
- Asymmetric Encryption: Also known as public key encryption, asysmmetric entryption relies on two keys- a public key  and a private key - to encryption and decryption data. the keys are generated using cryptographic algorithms and are mathematiallly connected such that data encrypted with the with teh public key can only be decrypted with the private key; while the private key must be kept secure to maintain the fidelity of this encryption paradigm,the public key can be openly shared. Asymmetric  key algorithms tend to be slower than their symmetric counterpart 
- SSL Certificate: A digital certificate grante to a server by a certificate authority. Contains the server's public key, to be used as part of the TLS handshake process in HTTPS connection
- A SSL certificate effectively confirms that a public key belongs to the server claming it belong to them, SSL certificates are crucial defense against main in the middle attacks  
- certificate Authority: A trusted entity that signs digital certificates- namely, SSL certificates that are relied on in HTTPS connection