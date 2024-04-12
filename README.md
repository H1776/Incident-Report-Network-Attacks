<h1> Incident Report: Network Attacks</h1>

<h2>Description</h2>
In this activity, I will consider a scenario involving a customer of the company that I work for who experiences a security issue when accessing the company’s website. I will  identify the likely cause of the service interruption. Then, I will explain how the attack occurred and the negative impact it had on the website. 
<br />

<h2>Scenario</h2>


I work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 

One afternoon, I received an automated alert from your monitoring system indicating a problem with the web server. I attempt to visit the company’s website, but I receive a connection timeout error message in my browser.

I use a packet sniffer to capture data packets in transit to and from the web server. I noticed a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. I suspect the server is under attack by a malicious actor. 

I take the server offline temporarily so that the machine can recover and return to a normal operating status. I also configured the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. I know that my IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. I need to alert my manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. I will need to be prepared to tell my boss about the type of attack I discovered and how it was affecting the web server and employees. <br/> <br/>

<p align="center">
LOG Information <br/> <br/>
<img src="https://imgur.com/AOLG0In.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/polyoXr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<h2>Section 1: Identify the type of attack that may have caused this network interruption </h2>

One potential explanation for the website’s connection timeout error message is a SYN flood attack. The logs show that there is a rapid influx of TCP SYN packets from an unfamiliar IP address. This event could be a SYN flood attack, a type of denial of service (DoS) attack where the attacker floods the target server with TCP SYN packets, overwhelming its ability to respond to legitimate connection requests. 
<br />
<br />

<h2>Section 2: Explain how the attack is causing the website to malfunction </h2>

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol:
1.	SYN: The client sends a SYN (synchronize) packet to the server, requesting to establish a connection.
2.	SYN-ACK: The server responds with a SYN-ACK (synchronize-acknowledgment) packer, indicating acknowledgment of the SYN packet and sending its own SYN packet.
3.	ACK: The client sends an ACK (acknowledgment) packet back to the server, confirming receipt of the server’s SYN packet and completing the handshake process. <br /> <br />

In a SYN flood attack, the malicious actor sends a flood of SYN packets to the target server without completing the three-way handshake. This overwhelms the server’s capacity to handle incoming connection requests and consumes its resources, leading to a denial of service for legitimate users. <br />

The logs indicate a rapid influx of TCP SYN packets form an unfamiliar IP address, suggesting a SYN flood attack. This flood of SYN packets consumes the server’s resources, such as CPU and memory, as it attempts to allocate resources for incomplete connections. As a result, the server becomes overwhelmed and is unable to respond to legitimate user requests, leading to connection timeouts and service interruptions for website visitors. <br /> <br />  

<h2>Analysis</h2>

Understanding network attacks involves recognizing various techniques used by malicious actors to disrupt or compromise network resources. These techniques include DDoS attacks, SYN floods, malware infections, phishing attempts, and more.

The symptoms described in the scenario, particularly the connection timeout error message and the overwhelming volume of TCP SYN packets, strongly suggest a SYN flood attack. This type of attack floods the target server with SYN packets, exhausting its resources and preventing it from handling legitimate connection requests.

The difference between a denial of service (DoS) and a distributed denial of service (DDoS) attack lies in the number of sources used to launch the attack. In a DoS attack, a single source overwhelms the target server with malicious traffic. In a DDoS attack, multiple sources coordinated by a central command target the victim simultaneously, amplifying the impact and making mitigation more challenging.

The website is taking a long time to load and reporting a connection timeout error because the server is overwhelmed by the flood of SYN packets. These packets consume the server's resources, leaving little capacity to handle legitimate connection requests. As a result, legitimate users experience delays or inability to access the website.

To prevent future attacks, the organization can implement various security measures such as rate limiting incoming connections, deploying intrusion detection systems (IDS) and intrusion prevention systems (IPS), using robust firewalls, and employing DDoS mitigation services. Additionally, regular security audits and updates to network infrastructure can help identify and patch vulnerabilities that attackers may exploit.
 
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
