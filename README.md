# secure-small-business-network
The purpose of this project is to design and secure a small-business network using Cisco Packet Tracer.
The goal was to segment traffic by department, enforce least-privilege access, manage IP addresses, and securely simulate internet connectivity. 
This network was designed to show real-world enterprise practices, including testing and troubleshooting. 
Tool used: Cisco Packet Tracer

**Network Architecture:** The network supports four departments.
  1 Router (Router-on-a-stick configuration)
  1 Layer 2 Switch
  4 End devices (PCs)
  Simulated Internet (Cloud)

| VLAN | Department | Subnet          | Purpose               |
| ---: | ---------- | --------------- | --------------------- |
|   10 | Management | 192.168.10.0/24 | Sensitive access      |
|   20 | IT         | 192.168.20.0/24 | Administrative access |
|   30 | Sales      | 192.168.30.0/24 | Business operations   |
|   40 | Guest      | 192.168.40.0/24 | Internet-only access  |

VLAN segmentation was implemented to isolate traffic and reduce the attack surface. Also, configuration of Inter-VLAN routing using a router-on-a-stick with 802.1Q trunking protocol between the switch and the router.

**Security Controls:** To enforce security policies, ACLs were applied on VLAN subinterfaces.
  - Guest VLAN was restricted to access internal networks.
  - Sales VLAN was blocked from accessing IT resources. 
  - IT VLAN had full access for administrative purposes. 

 **Network Services:** 
  - Configuration of DHCP on the router to dynamically assign IP addresses in each VLAN; this improved scalability and avoided manual configuration.
  - NAT overload (PAT) was implemented to translate private IP addresses to a public interface and simulate secure internet access. Since Packet Tracer has a cloud limitation, the NAT functionality was validated using router translation tables.

**Testing:** connectivity tests confirm the following 
  - Good VLAN isolation 
  - Correct inter-VLAN routing
  - Enforcement of access control policies
  - DHCP address assignment
  - Active NAT translations on outbound traffic
