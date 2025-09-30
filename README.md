# TASK4-firewalld
Dynamic Firewall management project (Firewalld)
This project demonstrates the practical application of Linux host-based firewall management using the firewalld utility, followed by verification using network socket monitoring tools like ss and nc (Netcat).
​The core objective was to dynamically manage firewall rules within the public zone and confirm those changes were correctly reflected in the system's network state.
Network Verification and Analysis:-
​After configuring the firewall, the following tools were used to verify the socket status:
​ss -tuln (Socket Statistics): Used to list all listening TCP and UDP sockets. The output successfully showed that the SSH service (port 22) was actively LISTENing on both IPv4 (0.0.0.0:22) and IPv6 ([::]:22) interfaces, confirming the underlying service was running and ready to accept connections.  
​nc -vz 127.0.0.1 22 (Netcat): Used to perform a local connection attempt to port 22. This successfully Connected to 127.0.0.1:22, which proves that the service is accessible and the firewall (at least on the loopback interface) is allowing the connection, a crucial step in testing service functionality.  
​This project successfully demonstrates the entire lifecycle of firewall management: Configuration, Commitment of Changes (Reload), and Verification using essential Linux utilities.
