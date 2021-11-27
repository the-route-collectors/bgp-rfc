# BGP The Reading List

The core of the core of BGP RFCs is RFC 4271. That RFC and its direct lineage is in **bold**.



## BGP Core RFCs

RFC 975 Autonomous Confederations

~~RFC 1267 A Border Gateway Protocol 3 (BGP-3) obsoletes 1105, 1163~~

~~RFC 1364 BGP OSPF Interaction~~

RFC 1403 BGP OSPF Interaction obsoletes 1364

~~RFC 1654 A Border Gateway Protocol 4 (BGP-4)~~

~~RFC 1656 BGP-4 Protocol Document Roadmap and Implementation Experience~~

~~RFC 1657 Definitions of Managed Objects for the Fourth Version of the Border Gateway Protocol (BGP-4) using SMIv2~~

RFC 1745 BGP4/IDRP for IP---OSPF Interaction

~~RFC 1771 A Border Gateway Protocol 4 (BGP-4) obsoletes 1654~~

~~RFC 1863 A BGP/IDRP Route Server alternative to a full mesh routing~~

~~RFC 1965 Autonomous System Confederations for BGP~~

~~RFC 1966 BGP Route Reflection An alternative to full mesh IBGP~~

RFC 1997 BGP Communities Attribute Updated by 7606, 8642

~~RFC 2283 Multiprotocol Extensions for BGP-4~~

~~RFC 2385 Protection of BGP Sessions via the TCP MD5 Signature Option~~

RFC 2439 BGP Route Flap Damping

RFC 2545 Use of BGP-4 Multiprotocol Extensions for IPv6 Inter-Domain Routing

RFC 2622 Routing Policy Specification Language (RPSL)

~~RFC 2796 BGP Route Reflection - An Alternative to Full Mesh IBGP~~

~~RFC 2842 Capabilities Advertisement with BGP-4~~

RFC 2918 Route Refresh Capability for BGP-4

RFC 3065 Autonomous System Confederations for BGP [Errata](http://www.rfc-editor.org/errata/rfc3065), Obsoletes [RFC 1965](http://www.rfc-editor.org/info/rfc1965), Obsoleted by [RFC 5065](http://www.rfc-editor.org/info/rfc5065)

~~RFC 3107 Carrying Label Information in BGP-4~~

~~RFC 3392 Capabilities Advertisement with BGP-4 obsoletes 2842~~

**RFC 4271 A Border Gateway Protocol 4 (BGP-4)** [Errata](http://www.rfc-editor.org/errata/rfc4271), Obsoletes [RFC 1771](http://www.rfc-editor.org/info/rfc1771), Updated by [RFC 6286](http://www.rfc-editor.org/info/rfc6286), [RFC 6608](http://www.rfc-editor.org/info/rfc6608), [RFC 6793](http://www.rfc-editor.org/info/rfc6793), [RFC 7606](http://www.rfc-editor.org/info/rfc7606), [RFC 7607](http://www.rfc-editor.org/info/rfc7607), [RFC 7705](http://www.rfc-editor.org/info/rfc7705), [RFC 8212](http://www.rfc-editor.org/info/rfc8212), RFC 8654, RFC 9072

RFC 4273 Definitions of Managed Objects for BGP-4

RFC 4456 BGP Route Reflection [Errata](http://www.rfc-editor.org/errata/rfc4456), Obsoletes [RFC 2796](http://www.rfc-editor.org/info/rfc2796), [RFC 1966](http://www.rfc-editor.org/info/rfc1966), Updated by [RFC 7606](http://www.rfc-editor.org/info/rfc7606)

~~RFC 4486 Subcodes for BGP Cease Notification Message~~ Updated by RFC 8203 (Obsoleted by RFC 9003)

RFC 4724 Graceful Restart Mechanism for BGP Updated by RFC [8538](https://tools.ietf.org/html/rfc8538) 

**RFC 4760 Multiprotocol Extensions for BGP-4**

RFC 4781 Graceful Restart Mechanism for BGP with MPLS

RFC 4797 Use of Provider Edge to Provider Edge (PE-PE) Generic Routing Encapsulation (GRE) or IP in BGP/MPLS IP Virtual Private Networks

~~RFC 4893 BGP Support for Four-octet AS Number Space~~ Obsoleted by 6793

RFC 5004 Avoid BGP Best Path Transitions from One External to Another

RFC 5065 Autonomous System Confederations for BGP [Errata](http://www.rfc-editor.org/errata/rfc5065), Obsoletes [RFC 3065](http://www.rfc-editor.org/info/rfc3065)

RFC 5195 BGP-Based Auto-Discovery for Layer-1 VPNs

RFC 5291 Outbound Route Filtering Capability for BGP-4

**[RFC 5492](https://www.rfc-editor.org/rfc/rfc5492.txt) Capabilities Advertisement with BGP-4**

RFC 5543 BGP Traffic Engineering Attribute

~~RFC 5566 BGP IPsec Tunnel Encapsulation Attribute~~

RFC 5668 4-Octet AS Specific BGP Extended Community

~~RFC 5594 Advertising IPv4 Network Layer Reachability Information with an IPv6 Next Hop~~

RFC 5701 IPv6 Address Specific BGP Extended Community Attribute

**RFC 6286 Autonomous-System-Wide Unique BGP Identifier for BGP-4**

**RFC 6608 Subcodes for BGP Finite State Machine Error** Updates 4271

RFC 6624 Layer 2 Virtual Private Networks Using BGP for Auto-Discovery and Signaling

RFC 6774 Distribution of Diverse BGP Paths

**RFC 6793 BGP Support for Four-Octet Autonomous System (AS) Number Space**

RFC 6811 BGP Prefix Origin Validation

RFC 6938 Deprecation of BGP Path Attributes: DPA, ADVERTISER, and RCID_PATH / CLUSTER_ID

RFC 7153 IANA Registries for BGP Extended Communities Updates 4360, 5701

RFC 7311 The Accumulated IGP Metric Attribute for BGP

RFC 7313 Enhanced Route Refresh Capability for BGP-4 Updates 2918

RFC 7353 Security Requirements for BGP Path Validation

RFC 7447 Deprecation of BGP Entropy Label Capability Attribute Updates 6790

**RFC [7705](https://tools.ietf.org/html/rfc7705) Autonomous System Migration Mechanisms and Their Effects on the BGP AS_PATH Attribute**

**RFC 7606 Revised Error Handling for BGP UPDATE Messages** Updates 1997, 4271, 4360, 4456, 4760, 5543, 5701, 6368

RFC [7607](https://tools.ietf.org/html/rfc7607) Codification of AS 0 Processing

RFC 7611 BGP ACCEPT_OWN Community Attribute

**RFC 7705 Autonomous System Migration Mechanisms and Their Effects on the BGP AS_PATH Attribute Updates 4271**

RFC 7752 North-Bound Distribution of Link-State and Traffic Engineering (TE) Information Using BGP

RFC 7900 Extranet Multicast in BGP/IP MPLS VPNs Updates 6513, 6514, 6625

RFC 7911 Advertisement of Multiple Paths in BGP

RFC 7947 Internet Exchange BGP Route Server

RFC 7964 Solutions for BGP Persistent Route Oscillation

RFC 8093 Deprecation of BGP Path Attribute Values 30, 31, 129, 241, 242, and 243

~~RFC 8203 BGP Administrative Shutdown Communication~~

**RFC [8212](https://tools.ietf.org/html/rfc8212) Default External BGP (EBGP) Route Propagation Behavior without Policies**

RFC 8326 Graceful BGP Session Shutdown

**RFC 8654 Extended Message Support for BGP**

RFC 8950 Advertising IPv4 Network Layer Reachability Information (NLRI) with an IPv6 Next Hop

RFC 9003 Extended BGP Administrative Shutdown Communication, Obsoletes 8203

**RFC 9072 Extended Optional Parameters Length for BGP OPEN Message** Updates 4271

RFC 9067 A YANG Data Model for Routing Policy



## Informational/historic RFCs

~~RFC 1163 (Historic) A Border Gateway Protocol (BGP) obsoletes 1105~~

RFC 1265 (Informational) BGP Protocol Analysis

RFC 1266 (Informational) Experience with the BGP Protocol

RFC 1397 (Historic) Default Route Advertisement In BGP2 And BGP3 Versions Of The Border Gateway Protocol

RFC 1773 Experience with the BGP-4 protocol obsoletes 1656

RFC 1774 (Informational) BGP-4 Protocol Analysis

RFC 1998 (Informational) An Application of the BGP Community Attribute in Multi-home Routing

RFC 2042 (Informational) Registering New BGP Attribute Types

RFC 3345 Border Gateway Protocol (BGP) Persistent Route Oscillation Condition

RFC 3765 (Informational) NOPEER Community for Border Gateway Protocol (BGP) Route Scope Control

RFC 3882 (Informational) Configuring BGP to Block Denial-of-Service Attacks

RFC 4098 (Informational) Terminology for Benchmarking BGP Device Convergence in the Control Plane

RFC 4264 (Informational) BGP Wedgies

RFC 4274 (Informational) BGP-4 Protocol Analysis

RFC 4275 (Informational) BGP-4 MIB Implementation Survey

RFC 4276 (Informational) BGP-4 Implementation Report

RFC 4277 (Informational) Experience with the BGP-4 Protocol

RFC 4272 BGP Security Vulnerabilities Analysis

RFC 4365 (Informational) Applicability Statement for BGP/MPLS IP Virtual Private Networks (VPNs)

RFC 4381 (Informational) Analysis of the Security of BGP/MPLS IP Virtual Private Networks (VPNs)

RFC 4451 (Informational) BGP MULTI_EXIT_DISC (MED) Considerations

RFC 5123 (Informational) Considerations in Validating the Path in BGP

RFC 5824 (Informational) Requirements for Supporting Customer Resource ReSerVation Protocol (RSVP) and RSVP Traffic Engineering (RSVP-TE) over a BGP/MPLS IP-VPN

RFC 6037 (Historic) Cisco Systems' Solution for Multicast in BGP/MPLS IP VPNs

RFC 6198 (Informational) Requirements for the Graceful Shutdown of BGP Sessions

RFC 6952 (Informational) Analysis of BGP, LDP, PCEP, and MSDP Issues According to the Keying and Authentication for Routing Protocols (KARP) Design Guide

RFC 7132 (Informational) Threat Model for BGP Path Security errata

RFC 7289 (Informational) Carrier-Grade NAT (CGN) Deployment with BGP/MPLS IP VPNs

RFC 7747 (informational) Basic BGP Convergence Benchmarking Methodology for Data-Plane Convergence

RFC 7789 (Informational) Impact of BGP Filtering on Inter-Domain Routing Policies

RFC 7814 (Informational) Virtual Subnet: A BGP/MPLS IP VPN-Based Subnet Extension Solution

RFC 7938 (Informational) Use of BGP for Routing in Large-Scale Data Centers

RFC 7948 (Informational) Internet Exchange BGP Route Server Operations



## Best Current Practice

RFC 4384 (Best Current Practice) BGP Communities for Data Collection

RFC 6472 (Best Current Practice) Recommendation for Not Using AS_SET and AS_CONFED_SET in BGP

RFC 7454 (Best Current Practice) BGP Operations and Security

RFC 8327 (Best Current Practice) Mitigating the Negative Impact of Maintenance through BGP Session Culling



## Experimental RFCs

~~RFC 1105 (Experimental) Border Gateway Protocol (BGP)~~

*RFC 5747 (Experimental) 4over6 Transit Solution Using IP Encapsulation and MP-BGP Extensions*

RFC 4576 Using a Link State Advertisement (LSA) Options Bit to Prevent Looping in BGP/MPLS IP Virtual Private Networks (VPNs)

RFC 4577 OSPF as the Provider/Customer Edge Protocol for BGP/MPLS IP Virtual Private Networks (VPNs)

RFC 4659 BGP-MPLS IP Virtual Private Network (VPN) Extension for IPv6 VPN

RFC 4684 Constrained Route Distribution for Border Gateway Protocol/MultiProtocol Label Switching (BGP/MPLS) Internet Protocol (IP) Virtual Private Networks (VPNs) Updates 4364



## Communities

RFC 1977 BGP Communities Attribute

RFC 4360 BGP Extended Communities Attribute

*RFC 4384 BGP Communities for Data Collection BCP 114*

RFC 5701 IPv6 Address Specific BGP Extended Community Attribute

RFC 7153 IANA Registries for BGP Extended Communities Updates 4360, 5701

RFC 8642 Policy Behavior for Well-Known BGP Communities

RFC 8092 BGP Large Communities

RFC 8097 BGP Prefix Origin Validation State Extended Community

*RFC 8195 Use of BGP Large Communities (informational)*

RFC 8642 Policy Behavior for Well-Known BGP Communities



## MRT

RFC 6396 Multi-Threaded Routing Toolkit (MRT) Routing Information Export Format

RFC 6397 Multi-Threaded Routing Toolkit (MRT) Border Gateway Protocol (BGP) Routing Information Export Format with Geo-Location Extensions

RFC 8050  Multi-Threaded Routing Toolkit (MRT) Routing Information Export Format with BGP Additional Path Extensions



## BMP

RFC 7854 BGP Monitoring Protocol (BMP)

RFC 8671 Support for Adj-RIB-Out in the BGP Monitoring Protocol (BMP)



## FlowSpec

RFC 8955 Dissemination of Flow Specification Rules

RFC 8956 Dissemination of Flow Specification Rules for IPv6

RFC 9117 Revised Validation Procedure for BGP Flow Specifications Updates 8955



## MPLS/VPN tunnels

~~RFC 2547 BGP/MPLS VPNs~~

RFC 4364 BGP/MPLS IP Virtual Private Networks (VPNs) Obsoletes 2547

RFC 4382 MPLS/BGP Layer 3 Virtual Private Network (VPN) Management Information Base

RFC 4761 Virtual Private LAN Service (VPLS) Using BGP for Auto-Discovery and Signaling

RFC 5512 The BGP Encapsulation Subsequent Address Family Identifier (SAFI) and the BGP Tunnel Encapsulation Attribute

RFC 6368 Internal BGP as the Provider/Customer Edge Protocol for BGP/MPLS IP Virtual Private Networks (VPNs)

RFC 6513 Multicast in MPLS/BGP IP VPNs

RFC 6514 BGP Encodings and Procedures for Multicast in MPLS/BGP IP VPNs

RFC 6515 IPv4 and IPv6 Infrastructure Addresses in BGP Updates for Multicast VPN

RFC 6517 Mandatory Features in a Layer 3 Multicast BGP/MPLS VPN Solution

RFC 7024 Virtual Hub-and-Spoke in BGP/MPLS VPNs

RFC 7432 BGP MPLS-Based Ethernet VPN

RFC 7441 Encoding Multipoint LDP (mLDP) Forwarding Equivalence Classes (FECs) in the NLRI of BGP MCAST-VPN Routes Updates 6514

RFC 7453 MPLS Transport Profile (MPLS-TP) Traffic Engineering (TE) Management Information Base (MIB)

RFC 7716 Global Table Multicast with BGP Multicast VPN (BGP-MVPN) Procedures

RFC 8277 Using BGP to Bind MPLS Labels to Address Prefixes



## BGPSec

RFC [8538](https://tools.ietf.org/html/rfc8538) Notification Message Support for BGP Graceful Restart

RFC 8608 BGPsec Algorithms, Key Formats, and Signature Formats Updates 8208

RFC 8205 BGPsec Protocol Specification

RFC 8206 BGPsec Considerations for Autonomous System (AS) Migration

RFC 8207 (Best Current Practice) BGPsec Operational Considerations

~~RFC 8208 BGPsec Algorithms, Key Formats, and Signature Formats Updates 7935~~

RFC 8209 A Profile for BGPsec Router Certificates, Certificate Revocation Lists, and Certification Requests Updates 6487
