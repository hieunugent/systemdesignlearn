
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

