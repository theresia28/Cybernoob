Scenario

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage  The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.”

![chrome_jd8ezyb2V1](https://github.com/theresia28/Cybernoob/raw/main/Networks%20and%20Network%20Security/UDP.png)

In the tcpdump log, you find the following information:

1. The first two lines of the log file show the initial outgoing request from your computer to the DNS server requesting the IP address of yummyrecipesforme.com. This request is sent in a UDP packet.

2. The third and fourth lines of the log show the response to your UDP packet. In this case, the ICMP 203.0.113.2 line is the start of the error message indicating that the UDP packet was undeliverable to port 53 of the DNS server.

3. In front of each request and response, you find timestamps that indicate when the incident happened. In the log, this is the first sequence of numbers displayed: 13:24:32.192571. This means the time is 1:24 p.m., 32.192571 seconds.

4. After the timestamps, you will find the source and destination IP addresses. In the first line, where the UDP packet travels from your browser to the DNS server, this information is displayed as: 192.51.100.15 > 203.0.113.2.domain. The IP address to the left of the greater than (>) symbol is the source address, which in this example is your computer’s IP address. The IP address to the right of the greater than (>) symbol is the destination IP address. In this case, it is the IP address for the DNS server: 203.0.113.2.domain. For the ICMP error response, the source address is 203.0.113.2 and the destination is your computer’s IP address 192.51.100.15.

5. After the source and destination IP addresses, there can be a number of additional details like the protocol, port number of the source, and flags. In the first line of the error log, the query identification number appears as: 35084. The plus sign after the query identification number indicates there are flags associated with the UDP message. The "A?" indicates a flag associated with the DNS request for an A record, where an A record maps a domain name to an IP address. The third line displays the protocol of the response message to the browser: "ICMP," which is followed by an ICMP error message.

6. The error message, "udp port 53 unreachable" is mentioned in the last line. Port 53 is a port for DNS service. The word "unreachable" in the message indicates the UDP message requesting an IP address for the domain "www.yummyrecipesforme.com" did not go through to the DNS server because no service was listening on the receiving DNS port.

7. The remaining lines in the log indicate that ICMP packets were sent two more times, but the same delivery error was received both times.

Now that you have captured data packets using a network analyzer tool, it is your job to identify which network protocol and service were impacted by this incident. Then, you will need to write a follow-up report. 

As an analyst, you can inspect network traffic and network data to determine what is causing network-related issues during cybersecurity incidents. Later in this course, you will demonstrate how to manage and resolve incidents. For now, you only need to analyze the situation. 

This event, in the meantime, is being handled by security engineers after you and other analysts have reported the issue to your direct supervisor. 

Network Traffic Analysis

## Part 1: Provide a summary of the problem found in the DNS and ICMP traffic log.

1. Use of UDP and ICMP in the DNS Protocol
UDP Protocol: Used by the browser to send requests to the DNS server to retrieve the IP address for the domain yummyrecipesforme.com.
ICMP Protocol: Returned an error message indicating an issue with contacting the DNS server.
2. Details of UDP and ICMP Messages in the Log
UDP Messages: Recorded in the first two lines of each log event, showing packets sent from the browser to the DNS server.
ICMP Error Messages: Displayed in the third and fourth lines with the error message "udp port 53 unreachable". Since port 53 is associated with DNS services, this indicates an issue with the DNS server.
3. Summary of tcpdump Log Analysis
Protocols Used: UDP for sending DNS requests and ICMP for returning error messages.
Indication of the Issue: The analysis shows that when the browser sends UDP packets to the DNS server, ICMP responds with the error message "udp port 53 unreachable". This implies that the DNS server is unresponsive.
4. Details from tcpdump Log
Logged Traffic: UDP packets from the source computer to the DNS server's IP address (203.0.113.2) on port 53 were recorded.
ICMP Response: The server returned the error message "udp port 53 unreachable" in response to the source computer.
Port 53: Identified as the standard port for DNS services, confirming that the issue lies with the DNS server.
5. Indications of DNS Operational Issues
Flags in the Log: The "+" symbol after the query ID indicates flags in the UDP message.
A Record Query Issues: The "A?" symbol suggests a failure in performing the query for an A record, which maps a domain name to an IP address.
6. Interpretation of Issues in the Log
Cause of the Issue: The unreachable port 53 indicates that the DNS server is not responding.
Potential Reasons: This could be caused by misconfiguration, system failure, or a Distributed Denial-of-Service (DDoS) attack targeting the DNS server.
Conclusion
The DNS server is experiencing issues because port 53 is unreachable, preventing the resolution of domain names to IP addresses. This problem is likely due to internal server failures or a DDoS attack targeting the DNS server.


## Part 2: Explain your analysis of the data and provide at least one cause of the incident

Summary for Each Point:
1. Incident Occurrence and Reporting Time
Time of Incident: The incident occurred at 1:24 PM today, as indicated by the timestamp in the log file: 13:24:32.192571 (24-hour format).
2. Event Reporting by Customers
Customer Reports: Customers reported receiving the error message “destination port unreachable” when attempting to access the website yummyrecipesforme.com.
3. Current Status of the Issue
Investigation Status: The issue is currently being investigated by the cybersecurity team to restore website access for customers.
4. Findings from Investigation
Network Analysis: Using tcpdump, network logs revealed that DNS port 53 is unreachable. The analysis involved sending UDP packets and receiving ICMP responses, with the error message “udp port 53 unreachable” being identified.
5. Next Steps for Troubleshooting
Determine DNS Server Status: Verify if the DNS server is down or experiencing an issue.
Firewall Configuration: Check the firewall settings to identify if traffic to port 53 has been inadvertently blocked. Firewalls often have the ability to block traffic on specific ports, which could be causing the issue.
6. Suspected Root Cause
Potential DoS Attack: The DNS server might have been overwhelmed by a Denial of Service (DoS) attack, making it unable to respond to legitimate traffic.
Firewall Misconfiguration: Alternatively, a firewall misconfiguration may have blocked network traffic on port 53.
Conclusion
The incident was first reported at 1:24 PM when customers encountered "destination port unreachable" errors. Investigation through tcpdump logs revealed that DNS port 53 is unreachable. Possible causes include a DoS attack on the DNS server or a firewall misconfiguration blocking traffic on port 53. Further troubleshooting is required to confirm the root cause and resolve the issue.

