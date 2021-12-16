
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