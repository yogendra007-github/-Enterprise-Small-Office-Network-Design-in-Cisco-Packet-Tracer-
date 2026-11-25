# -Enterprise-Small-Office-Network-Design-in-Cisco-Packet-Tracer-
I recently designed and implemented a complete, standalone branch office network architecture from scratch in Cisco Packet Tracer—built to mirror a real-world enterprise deployment with strict departmental segmentation, automated IP management, and wireless mobility.

🏗️ Architecture & Network Design

Core Infrastructure: Deployed a Cisco 2911 Router and a Cisco Catalyst 2960-24TT Switch supporting both wired workstations/printers and dedicated wireless Access Points across three departments.

Subnetting (192.168.1.0/24 → three /26 subnets):

🟡 Admin / IT (VLAN 10): 192.168.1.0/26 (Usable: .1 – .62 | Mask: 255.255.255.192)

🟢 Finance / HR (VLAN 20): 192.168.1.64/26 (Usable: .65 – .126 | Mask: 255.255.255.192)

🟠 Customer Service (VLAN 30): 192.168.1.128/26 (Usable: .129 – .190 | Mask: 255.255.255.192)

⚙️ Key Technical Implementations

VLAN Segmentation & 802.1Q Trunking: Isolated broadcast domains across switch access ports for each department and configured an 802.1Q trunk link to the router.

Inter-VLAN Routing (Router-on-a-Stick): Configured subinterfaces (Gi0/0.10, Gi0/0.20, Gi0/0.30) with dot1Q encapsulation to enable seamless cross-departmental communication.

Automated DHCP Pools: Set up router-based DHCP pools for each /26 subnet so wired PCs, laptops, and smartphones dynamically lease IPv4 addresses, subnet masks, and default gateways.

Enterprise Wireless Integration: Configured department-specific Access Points (Access Point0, Access Point1, Access Point2) with dedicated SSIDs and WPA2-PSK security so mobile clients stay segmented within their respective VLANs.

Switch Hardening & Remote Management: Secured CLI access with encrypted passwords, MOTD banners, SSHv2 (RSA 1024-bit), and VTY Access Control Lists (ACLs).

✅ End-to-End Verification

Tested and verified full connectivity—from dynamic DHCP lease acquisition across wired and wireless hosts to successful cross-VLAN ICMP pings between Admin/IT, Finance/HR, and Customer Service.
