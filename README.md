# NETWORKWALKS-FOOTPRINTING-AND-ZENMAPPING
Doing networkwalks footprinting and zenmap
WEEK 2 CYBERSECURITY PROJECT REPORT
FOOTPRINTING & RECONNAISSANCE (W2-PM1)  |  NETWORK SCANNING WITH ZENMAP (W2-PM5)

Programme	Cybersecurity & Ethical Hacking – Week 2 B084
Modules	W2-PM1 Footprinting with Multiple Kali Tools; W2-PM5 Zenmap Network Scanning
Footprinting target	networkwalks.com (course-assigned target)
Network scope	User's own local Wi-Fi / hotspot network
Local IPv4	192.......57..
Subnet mask / subnet	255.......0 / 192.....57
Default gateway	192......57.
Local Wi-Fi MAC	5C-51-4F-EC-F2-ED

Report date	10 November 2026


1. Liability Disclaimer
These activities were performed for educational purposes within the assigned lab scope. Local network discovery was limited to my own network. No exploitation, password attacks or disruption were attempted. Testing must only be performed on systems and networks for which appropriate authorization has been granted. Observations in this report are not proof of exploitable vulnerabilities.

2. Introduction
This report documents two Week 2 practical modules. W2-PM1 introduces footprinting and reconnaissance against networkwalks.com using six Kali Linux tools. W2-PM5 covers local network discovery using Zenmap on my own Wi-Fi/hotspot network. Together, these activities demonstrate public-information gathering and the discovery of live hosts within an authorized local network.
The report follows the structure of the supplied sample report. Example IP addresses, MAC addresses, software versions and WAF results from the sample or course guide are not treated as my own findings.

3. Tools Used
Tool / Environment	Purpose

Kali Linux terminal	Environment for W2-PM1 commands.

WHOIS	Queries public domain registration information.

WhatWeb	Fingerprints technologies exposed by a website.

Nslookup	Queries DNS to resolve a domain.

Curl -I	Requests HTTP response headers.

Wafw00f	Checks for indicators of a Web Application Firewall.

DNSRecon	Enumerates DNS records.

Windows Command Prompt	Used ipconfig and ARP information for local network inspection.

Zenmap / Nmap	Performs host discovery and displays scan/topology information.

4. Activities Performed

4.1 Footprinting & Reconnaissance – W2-PM1
The assigned target was networkwalks.com. The practical requires six Kali Linux tools. The commands and evidence status are listed below.

Task – WHOIS
Command: whois networkwalks.com
Observed result / status: Attempted. Successful, Gave the domain name and all necessary information.

Task – WhatWeb
Command: whatweb networkwalks.com
Observed result / status: Command specified by the lab; Gave the appache, java script used, email used by the domain and other necessary information.

Task – Nslookup
Command: nslookup networkwalks.com
Observed result / status: Command specified by the lab; Successful, Domain I p adress was found and located

Task – Curl headers
Command: curl -I https://networkwalks.com
Observed result / status: Command specified by the lab; It gave a response of Http 200 ok

Task – Wafw00f
Command: wafw00f networkwalks.com
Observed result / status: Command specified by the lab; Gave me spiderweb as the WAF of the website

Task – DNSRecon
Command: dnsrecon -d networkwalks.com
Observed result / status: Command specified by the lab; Gave me SPV, SOA and the Bind version and other things.

4.2 Network Scanning with Zenmap – W2-PM5

I used Zenmap's Ping Scan against my own local subnet, 192.....57....
Local IP/subnet
IPv4 192.168.57.199; mask 255.........0; subnet 192......57; gateway 192......57.

Zenmap scan

Ping Scan target 192.....57. Recorded result: one host up, 192.***.**.199.
Host count/IPs
One host responded in the recorded scan: 192.......199. This does not prove no other devices were connected.

MAC addresses
PC Wi-Fi MAC: 5C-51-4F-EC-F2-ED. Earlier ARP output showed gateway 192.........199 with MAC 6A-F3-E9-38-D2-1A.

ARP interpretation
192.168.56.255 → ff-ff-ff-ff-ff-ff and 224.0.0.22 / .251 / .252 plus 239.255.255.250 mappings are broadcast/multicast entries, not verified extra device MACs. 192.168.56.255 is outside 192.168.57.0/24.

Topology PDF
 
5. Risk Analysis / Impact
The assessment below is limited to the evidence available.

Observation	Potential impact / evidence	Assessment

Observation	Potential impact / evidence	Assessment

Public technology details	Could assist attackers in selecting further checks; actual WhatWeb result not supplied.	Medium

Domain / DNS exposure	Could reveal administrative or infrastructure information; WHOIS failed and other DNS output is missing.	Low

HTTP headers	May assist technology fingerprinting; actual Curl output missing.	Low

WAF identification	May reveal defensive architecture; actual Wafw00f output missing.	Low

Local host visibility	The scan identified the user's own PC; unknown devices should be verified.	Medium

Incomplete host discovery	One responding host does not establish that no other devices were connected.	Medium

These are information-gathering observations and limitations, not confirmed vulnerabilities. No exploitation or vulnerability validation was performed.

6. Recommendations

1.	Retry WHOIS when DNS/name resolution is working and save the complete output.

2.	Run WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon; save genuine outputs and screenshots.

3.	If a command fails, record the exact error rather than replacing it with assumed or sample values.

4.	Confirm the active Windows adapter and subnet with ipconfig before scanning.

5.	If checking another hotspot device, record its IP from that device's Wi-Fi details and verify it only within the authorized local
network.
6.	Interpret Zenmap discovery alongside ARP and device-side information; missing responses must be treated cautiously.

7.	Export the Zenmap Topology view to PDF and include it when completed.

8.	Keep screenshots, command outputs and the final report together in a clearly named evidence folder.

9.	Perform reconnaissance and scanning only within an authorized scope.

7. Limitations & Outstanding Evidence

⦁	At first only the WHOIS error was supplied as an actual PM1 result; the other five PM1 outputs are outstanding.

⦁	The recorded Zenmap Ping Scan showed one host up. Discovery scans can miss devices that do not respond to probes, are asleep, filtered, 
or isolated by network configuration.

⦁	A second phone was connected during troubleshooting, but its IP address and MAC were not verified; it is not listed as a confirmed discovered host.

⦁	The topology PDF export has not been confirmed as completed.

8. Conclusion

The two practical modules introduced complementary information-gathering stages. W2-PM1 provided practice with tools for examining public domain registration, web technologies, DNS, HTTP headers and WAF indicators. My WHOIS attempt was successful. In W2-PM5, I identified my local network configuration and ran a Zenmap Ping Scan against 192.168.57.0/24. The recorded scan showed my PC as one responding host. The exercise reinforced that broadcast/multicast ARP mappings are not additional devices and that scan results must be interpreted in light of network conditions.

9. Evidence / Screenshots
Evidence 1 – WHOIS attempt (PM1)

![Screenshot description](Images%20./Screenshoot1.PNG)

Capture actual whatweb networkwalks.com output.
Evidence 3 – Nslookup and Curl outputs (PM1)

![Screenshot 3](Images%20./Screenshot3.png)

Capture actual DNS lookup and HTTP header outputs.
Evidence 4 – Wafw00f and DNSRecon outputs (PM1)

![Screenshot 4](Images%20./Screenshot4.png)

![Screenshot 5](Images%20./Screenshot5.png)



Capture WAFw00f
Evidence 5 – WAFw00f (PM5)

![Screenshot 6](Images%20./Screenshot6.png)


Show IPv4 address, subnet mask and gateway.
Evidence 6 – Zenmap Ping Scan (PM5)

![Screenshot 8](Images%20./Screenshot8.png)

Show ipconfig results
Evidence 7 – Ipconfig

![Screenshot 10](Images%20./Screenshot10.png)

Capture dnsrecon -d networkwalks.com
Evidence 8 - Dns

![Screenshot 7](Images%20./Screenshot07.png)


10. Project Information


Programme: Cybersecurity & Ethical Hacking | Week: 02 | Modules: W2-PM1 and W2-PM5

Author: Victor Ebubechukwu

Linkedin link:
