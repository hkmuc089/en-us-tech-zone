---
layout: doc
description: Learn how Citrix SD-WAN Advanced Edition provides Edge Security for your Enterprise network.
---
# Citrix SD-WAN Edge Security

## Contributors

**Author:** [Matthew Brooks](https://twitter.com/tweetmattbrooks)

**Special Thanks** Ravi Pegada

## Introduction

With the continued growth cloud and SaaS, Enterprises are searching for solutions to provide optimal Internet access irrespective of where the endpoint is located. Citrix SD-WAN excels at steering intranet-bound traffic across the WAN or Internet-bound traffic, at the Edge, using business rules for 4.500+ predefined applications.

However, in order to provide direct Internet access Enterprises also need to secure remote offices to protect the intranet. Direct Internet access exposes remote networks, and subsequently the entire corporate network, to threats. Ingress and egress traffic must be filtered, inspected, and scanned to protect against vulnerabilities.  

Citrix SD-WAN has a native [onboard ICSA certified firewall](https://www.citrix.com/blogs/2019/08/13/do-you-trust-your-sd-wan-firewall/), and integrates with leading third party [Secure Web Gateway (SWG)](/en-us/citrix-sd-wan/11-2/internet-service/dia-with-secure-web-gateway.html) vendors via cloud proxy, or through onboard hosted [Virtual Network Function (VNF)](https://www.citrix.com/blogs/2020/05/14/citrix-check-point-software-support-choice-in-protecting-the-wan-edge/). Security partners include:

*  [iBoss](/en-us/citrix-sd-wan/11-2/security/citrix-sd-wan-secure-web-gateway/iboss-integration.html)
*  [Check Point](/en-us/citrix-sd-wan/11-2/hosted-firewalls/checkpoint-integration-on-1100-platform.html)
*  [Palo Alto](/en-us/citrix-sd-wan/11-2/security/citrix-sd-wan-secure-web-gateway/palo-alto-integration-by-using-ipsec--tunnels.html)
*  [Force Point](/en-us/citrix-sd-wan/11-2/security/citrix-sd-wan-secure-web-gateway/firewall-traffic-redirection-support-by-using-forcepoint.html)
*  [Zscaler](/en-us/citrix-sd-wan/11-2/security/citrix-sd-wan-secure-web-gateway/sd-wan-web-secure-gateway-using-gre-tunnels-and-ipsec-tunnels.html)

Now Citrix has added native onboard Next Generation Firewall – Edge Security functionality to the arsenal of SD-WAN protection options. The release of Citrix SD-WAN version 11.2 Advanced Edition combines full stack security functionality, with its market leading application performance enhancement capabilities, including:

*  [Intrusion Prevention](/en-us/tech-zone/design/design-decisions/citrix-sdwan-home-office.html)
*  [Web Filtering](/en-us/tech-zone/design/design-decisions/citrix-sdwan-home-office.html)
*  [Malware Protection](/en-us/tech-zone/design/design-decisions/citrix-sdwan-home-office.html)

As a result, Enterprises can now enhance application performance securely from the edge of their network entirely with Citrix. They can confidently consolidate their Branch Office networks with a Citrix SD-WAN appliance that can provide steering to Internet services while inspecting traffic, and protecting it. They also can manage and monitor Edge Security through a single plane of glass with Citrix Cloud hosted Orchestrator service.

## Getting Started

With only a handful of requirements, Citrix SD-WAN customers can quickly get up and running with Advanced Edition - Edge Security:

*  [Citrix Orchestrator](/en-us/citrix-sd-wan-orchestrator/network-level-configuration/security.html#intrusion-prevention)
*  [11.2+ software](/en-us/citrix-sd-wan/11-2.html)
*  [1100 AE appliance](https://www.citrix.com/content/dam/citrix/en_us/documents/data-sheet/citrix-sd-wan-data-sheet.pdf)
*  [Advanced Edition (AE) license](/en-us/citrix-sd-wan/11-2.html#citrix-sd-wan-platform-editions)
*  [Firewall Security Profile](/en-us/citrix-sd-wan-orchestrator/network-level-configuration/edge-security.html#security-profiles)
*  [Firewall Policy Action](/en-us/citrix-sd-wan-orchestrator/network-level-configuration/edge-security.html#edge-security-firewall-policy)

### Network Configuration  – Software Version 11.2.0.88 & 1100 appliance

![Network Configuration](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_networkconfiguration.png)

### Basic Settings – Device Edition AE

![Basic Settings](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_basicsettings.png)

### Firewall Security Profile

![Firewall Security Profile](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_firewallsecurityprofile.png)

### Firewall Policy Action

![Firewall Policy Action](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_firewallpolicyaction.png)

## Intrusion Prevention

Intrusion Prevention Systems (IPS) mitigate the risk of threats to networks by identifying, logging and or blocking known attacks.  The patterns of attacks are regularly updated and added to a common database. Citrix SD-WAN Edge Protection – Intrusion Prevention includes over 34,000 signature detections and heuristic signatures for port scans.

![Intrustion Prevention](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_intrustionprevention.png)

Citrix SD-WAN Edge Security Intrusion Prevention functionality is powered by the [Suricata](http://suricata-ids.org/) open source network threat detection engine. Suricata is owned and supported by the Open Information Security Foundation (OISF). It inspects the network traffic after passing through firewall using extensive rules and a powerful signature language.

Rules look for attacks such as port scans where bots or bad actors test for open ports susceptible to penetration; any traffic from known “bad” public IP addresses; or Denial of Service attacks where attackers seek to overrun network bandwidth and receive buffers by sending certain protocol sequences excessively or a high volume of flows.

![Intrustion Prevention Profile](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_ipsprofile.png)

Citrix SD-WAN Intrusion Prevention includes predefined rules grouped into one of four priority categories based on severity:

*  Critical
*  High
*  Medium
*  Low

![Intrustion Prevention Rule](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_ipsrule.png)

Rules, which are customizable, include fields to specify patterns to identify in a logical statement. Once matched the following actions can be taken:

*  Recommended - Perform the recommended action defined for the signatures.
*  Enable Log - Allow and log the traffic matching any of the signatures in the rule.
*  Whitelist - The signature’s source and destination networks are modified to exclude networks defined by the whitelist variable.
*  Disable - The signatures are disabled. Allow the traffic to continue to the destination without logging.
*  Enable Block - Drop the traffic matching any of the signatures in the rule
*  Enable Block of Recommended is Enabled - If the rule action is Recommended and the signature’s recommended action is Enable Log, drop the traffic matching any of the signatures in the rule.

For more information see [Citrix SD-WAN Edge Security – Intrusion Prevention](/en-us/citrix-sd-wan-orchestrator/network-level-configuration/security.html#intrusion-prevention)

## Web Filtering

Web Filtering mitigates the risk of unsuspecting users clicking links on sites behind known “unsafe” domains and infecting their endpoints with malware, viruses, ransomware or other threats. It also helps protect users from accessing sites that would violate compliance rules or the Enterprise Acceptable Use Policy.

![Web Filtering](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_webfiltering.png)

Citrix SD-WAN utilizes [WebRoot’s BrightCloud](https://www.webroot.com/us/en/business/threat-intelligence/internet/web-classification-and-reputation-services) real-time, machine learning-based Web Classification and Web Reputation engine to filter domain names. It includes over thirty-two (32) billion URLs and seven hundred fifty (750) million domains. When users visit a site, the URL is sent for classification in real time. A temporary local cache is maintained to expedite the lookup the next time the URL is requested.

Web filtering is enabled, and preferences are configured within a Security Profile.

![Web Filtering Security Profile](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_webfilteringsecurityprofile.png)

Existing categories may be selected to “block” access to the web site or “flag” (log) access.  Alternatively, specific sites may be “bypassed” by domain name or IP address.

![Web Filtering Categories](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_webfilteringsecuritycategories.png)

For more information see [Citrix SD-WAN Edge Security – Web Filtering](/en-us/citrix-sd-wan-orchestrator/network-level-configuration/edge-security.html#web-filtering)

## Anti-Malware

Anti-Malware guards against ransomware and viruses by protecting users from unsafe files delivered by HTTP download or opened from SMTP delivered email. Powered by  [Bitdefender](https://www.bitdefender.com/), it assembles and scans files destine for users through email or http downloads. It can block the file delivery, log its presence, and or include a notification regarding the risk identified.

![Anti-Malware](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_antimalware.png)

Citrix SD-WAN Anti-Malware takes a four-step process to evaluate files. It has the ability to scan 41 file-type extensions and 10 MIME types for email content. If the file fails any of the tests below it is considered malware and the download is blocked:

1.  collect metadata about the file and query a threat intelligence database for information about the file based on its fingerprint.
1.  locally scan using Bitdefender's signature database will be run on the server while the cloud lookup is being performed.
1.  Perform a heuristic scan to look for suspicious patterns in executable files.
1.  lastly, dynamic analysis is performed by evaluating code in a emulator and looking for malicious activity.

![Anti-Malware Security Profile](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_antimalwaresecurityprofile.png)

Anti-Malware may be enabled or disabled for specific file types by selecting their file extension.

![Anti-Malware File Types](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_antimalwarefiletypes.png)

Also, you can choose to exclude certain MIME types from scanning.

![Anti-Malware MIME Types](/en-us/tech-zone/learn/media/tech-briefs_citrix-sdwan-edge-security_antimalwaremimetypes.png)

For more information see [Citrix SD-WAN Edge Security – Anti-Malware](/en-us/citrix-sd-wan-orchestrator/network-level-configuration/edge-security.html#anti-malware)

## Differentiation

With Edge Security, that comes with 11.2 Advanced Edition, Citrix is now one of the few SD-WAN vendors that provides Intrusion Detection, Web Filtering, and Anti-Malware natively in On-premises appliances.  With Edge Security Citrix SD-WAN offers significant value to Enterprises including:

*  **Maximize User Experience & Minimize Network Bandwidth** – Enterprises no longer need to backhaul internet traffic over their Wan to meet compliance requirements and protect their endpoints from the perils of the Internet. Now they can protect endpoints and steer flows to the nearest business SaaS sites.
*  **Secure the Enterprise Perimeter** – while direct Internet access enables better application performance it exposes branches and subsequently the corporate network to risk. Edge Security mitigates that risk by guarding against vulnerabilities at the point of remote office Internet access.
*  **Branch Office consolidation** – Enterprises can simplify what they need to manage and host in remote office utility closets.  Stand alone routers, SWG appliances and firewalls, DHCP and DNS servers, or WAN Optimization device functionality may all be replaced with a Citrix SD-WAN 1100 AE appliance.
*  **Single Point of Contact** – customers can contact Citrix regarding Network forwarding or Network security. Having a single point of contact avoids finger pointing if complex issues should arise.  Enterprises can partner with Citrix Services to support mission critical operations.
*  **Simplified Monitoring & Management** -  with Citrix Cloud hosted Orchestrator service Enterprise admins have an easy to use dashboard to onboard, configure, and monitor their Citrix SD-WAN Edge Security implementations.

## Summary

Enterprises can provide a great Internet service user experience while securing their intranet at Edge egress points with **Citrix SD-WAN Edge Security**. With the **.2 Advanced Edition** Citrix provides **Intrusion Prevention, Web Filtering, and Anti-Malware** on the **SD-WAN 1100 AE appliance**. User endpoints are protected in their Home and Branch Offices, while Administrators manage and monitor their network centrally through the Citrix Cloud hosted Orchestrator service.