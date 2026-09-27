# Northbridge Hybrid Network

## Overview

This project documents the design, implementation, and validation of a hybrid network that connects a local network environment with AWS. The project includes local network segmentation, routing, access controls, cloud networking, site to site VPN connectivity, and security validation across both environments.

The repository contains the project network diagram and screenshots from eight test cases used to verify that the design worked as intended.

## Project Scope

The project covers:

- Local network segmentation with VLANs and 802.1Q trunking
- Local routing, DHCP, static addressing, and external access
- Firewall based access control between local network segments
- AWS network segmentation
- AWS public and private routing
- Cloud reachability and security group validation
- Site to site VPN connectivity using WireGuard
- Hybrid network security testing across the local and AWS environments

## Architecture

The local side of the environment uses segmented VLANs, switching, local clients, a local server, and VyOS for routing and firewall control. The AWS side uses segmented cloud networking with public and private resources, route tables, and security groups.

The two environments are connected through a WireGuard site to site VPN. This allows approved traffic from the local network to reach resources in the AWS private network while keeping access controlled on both sides.

## Network Diagram

![Northbridge network diagram](Northbridge/BSCNE%20Capstone%20Network%20Diagram.png)

## Test Case 1: Local Network Segmentation

The first test case validates Layer 2 segmentation using VLANs and 802.1Q trunking. The evidence includes the network segment, VLAN configuration on SW1 and SW2, and successful trunk connectivity tests for VLAN 10 and VLAN 20.

![Local network segmentation](Northbridge/Test%20Case%20%231%20-%20Local%20Networks%20-%20Basic%20Network%20Segmentation%20at%20Layer%202%20via%20VLANs%20and%20802.1q%20-%20Network%20Diagram%20or%20Segment.png)

![SW1 VLAN configuration](Northbridge/Test%20Case%20%231%20-%20Local%20Networks%20-%20Basic%20Network%20Segmentation%20at%20Layer%202%20via%20VLANs%20and%20802.1q%20-%20Process%20List%20-%20SW1%20VLAN%20Configuration.png)

![VLAN 10 trunk test](Northbridge/Test%20Case%20%231%20-%20Local%20Networks%20-%20Basic%20Network%20Segmentation%20at%20Layer%202%20via%20VLANs%20and%20802.1q%20-%20Testing%20Method%20-%20VLAN%2010%20Trunk%20Ping.png)

## Test Case 2: Local Routing and External Access

The second test case validates local addressing and routing. The screenshots show DHCP operation for local clients, a static address for the local server, and VyOS routing used for external access.

![Admin PC DHCP](Northbridge/Test%20Case%20%232%20-%20Local%20Networks%20-%20Accessing%20External%20Resources%20-%20Routing%20and%20Traffic%20Security%20-%20Testing%20Method%20-%20Admin-PC-1%20DHCP.png)

![Local server static address](Northbridge/Test%20Case%20%232%20-%20Local%20Networks%20-%20Accessing%20External%20Resources%20-%20Routing%20and%20Traffic%20Security%20-%20Testing%20Method%20-%20Local%20Server%20Static%20Address.png)

![VyOS routing and external access](Northbridge/Test%20Case%20%232%20-%20Local%20Networks%20-%20Accessing%20External%20Resources%20-%20Routing%20and%20Traffic%20Security%20-%20Testing%20Method%20-%20VyOS%20Routing%20and%20External%20Access.png)

## Test Case 3: Local Device Discovery and Reachability

This test case validates local firewall policy and controlled reachability. The evidence shows VyOS firewall rules, permitted admin access, and blocked support access where required.

![VyOS firewall rules](Northbridge/Test%20Case%20%233%20-%20Local%20Networks%20-%20Device%20Discovery%20and%20Reachability%20-%20Process%20List%20-%20VyOS%20Firewall%20Rules.png)

![Admin access allowed](Northbridge/Test%20Case%20%233%20-%20Local%20Networks%20-%20Device%20Discovery%20and%20Reachability%20-%20Testing%20Method%20-%20Admin%20Access%20Allowed.png)

![Support access blocked](Northbridge/Test%20Case%20%233%20-%20Local%20Networks%20-%20Device%20Discovery%20and%20Reachability%20-%20Testing%20Method%20-%20Support%20Access%20Blocked.png)

## Test Case 4: AWS Network Segmentation

The fourth test case documents the cloud network layout and segmentation used in AWS.

![AWS network segmentation](Northbridge/Test%20Case%20%234%20-%20Cloud%20Networks%20-%20Network%20Segmentation%20-%20Network%20Diagram%20or%20Segment.png)

## Test Case 5: AWS Routing and External Access

This test case validates public and private routing in AWS. The evidence includes the private route table, public routing configuration, public web server access, and the public and private IP addressing used in the environment.

![Private route table](Northbridge/Test%20Case%20%235%20-%20Cloud%20Networks%20-%20Accessing%20External%20Resources%20-%20Routing%20and%20Traffic%20Security%20-%20Process%20List%20-%20Private%20Route%20Table.png)

![Public web server access](Northbridge/Test%20Case%20%235%20-%20Cloud%20Networks%20-%20Accessing%20External%20Resources%20-%20Routing%20and%20Traffic%20Security%20-%20Testing%20Method%20-%20Public%20Web%20Server%20Access.png)

![Public and private IP addressing](Northbridge/Test%20Case%20%235%20-%20Cloud%20Networks%20-%20Accessing%20External%20Resources%20-%20Routing%20and%20Traffic%20Security%20-%20Testing%20Method%20-%20Public%20and%20Private%20IP%20Addressing.png)

## Test Case 6: AWS Device Discovery and Reachability

This test case validates cloud reachability controls. The screenshots show permitted access to the web server and blocked access from an unauthorized test client.

![Web server access allowed](Northbridge/Test%20Case%20%236%20-%20Cloud%20Networks%20-%20Device%20Discovery%20and%20Reachability%20-%20Testing%20Method%20-%20Web%20Server%20Access%20Allowed.png)

![Unauthorized client blocked](Northbridge/Test%20Case%20%236%20-%20Cloud%20Networks%20-%20Device%20Discovery%20and%20Reachability%20-%20Testing%20Method%20-%20Unauthorized%20Test%20Client%20Blocked.png)

## Test Case 7: Site to Site VPN Connectivity

The seventh test case validates connectivity between the local network and AWS using WireGuard. The evidence shows the VPN security group rules, an active WireGuard tunnel, connectivity from the local network to the AWS private subnet, and troubleshooting steps used to confirm the tunnel was responsible for hybrid connectivity.

![VPN security group rules](Northbridge/Test%20Case%20%237%20-%20Site%20to%20Site%20VPN%20Connectivity%20-%20Process%20List%20-%20VPN%20Security%20Group%20Rules.png)

![Active WireGuard tunnel and ping](Northbridge/Test%20Case%20%237%20-%20Site%20to%20Site%20VPN%20Connectivity%20-%20Testing%20Method%20-%20Active%20WireGuard%20Tunnel%20and%20Ping.png)

![Local network to AWS private subnet](Northbridge/Test%20Case%20%237%20-%20Site%20to%20Site%20VPN%20Connectivity%20-%20Testing%20Method%20-%20Local%20Network%20to%20AWS%20Private%20Subnet.png)

The project also includes evidence of the AWS WireGuard tunnel being disabled and restored, along with source destination check configuration on the VPN gateway.

## Test Case 8: Hybrid Network Security

The final test case validates security controls across the hybrid environment. The evidence shows the final application security group rules, admin SSH access being allowed, and support application access being allowed while SSH is blocked.

![Final application security group rules](Northbridge/Test%20Case%20%238%20-%20Hybrid%20Network%20Security%20-%20Process%20List%20-%20Final%20Application%20Security%20Group%20Rules.png)

![Admin SSH access allowed](Northbridge/Test%20Case%20%238%20-%20Hybrid%20Network%20Security%20-%20Testing%20Method%20-%20Admin%20SSH%20Access%20Allowed.png)

![Support application access allowed and SSH blocked](Northbridge/Test%20Case%20%238%20-%20Hybrid%20Network%20Security%20-%20Testing%20Method%20-%20Support%20Application%20Access%20Allowed%20and%20SSH%20Blocked.png)

## Troubleshooting and Validation

The project was tested by checking both successful and failed traffic instead of only confirming that devices could communicate.

During VPN testing, I disabled the AWS WireGuard tunnel and confirmed that the local network could no longer reach the AWS private network. I then restored the tunnel and verified that connectivity returned. I also validated the VPN gateway configuration, including the source destination check setting required for forwarded traffic.

Access controls were tested in the same way. Admin traffic was allowed where required, while support and unauthorized test clients were blocked from services they were not supposed to reach. These tests helped confirm that the firewall rules and AWS security groups were enforcing the intended design.

## Skills Demonstrated

- VLAN design and 802.1Q trunking
- Layer 2 network segmentation
- DHCP and static IP addressing
- Routing with VyOS
- Firewall policy and traffic control
- AWS VPC networking
- Public and private subnet design
- Route table configuration
- AWS security groups
- WireGuard VPN configuration and validation
- Hybrid network troubleshooting
- Connectivity and security testing

## Repository Structure

```text
Northbridge Hybrid Network/
├── README.md
└── Northbridge/
    ├── BSCNE Capstone Network Diagram.png
    └── Test Case screenshots
```

## Project Evidence

The screenshots in the `Northbridge` folder are the original project evidence. They are named by test case, process step, and testing method so the implementation and validation can be followed from the repository itself.
