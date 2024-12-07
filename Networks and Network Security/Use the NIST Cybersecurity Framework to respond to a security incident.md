# Cybersecurity Incident Scenario and Response Plan

## Scenario
A multimedia company offering web design, graphic design, and social media marketing solutions experienced a Distributed Denial of Service (DDoS) attack. This attack compromised the internal network for two hours, during which:

- Network services stopped responding due to a flood of ICMP packets.
- Normal internal traffic was unable to access network resources.

### Response by Incident Management Team
1. Blocked incoming ICMP packets.
2. Stopped all non-critical network services.
3. Restored critical network services.

### Findings from Investigation
The cybersecurity team discovered:
- A malicious actor exploited an unconfigured firewall to send ICMP ping floods.
- This vulnerability allowed the attack to overwhelm the network.

### Mitigation Measures Implemented
1. A new firewall rule to limit the rate of incoming ICMP packets.
2. Source IP address verification on the firewall to check for spoofed IP addresses.
3. Network monitoring software to detect abnormal traffic patterns.
4. An IDS/IPS system to filter ICMP traffic with suspicious characteristics.

---

## Applying the NIST Cybersecurity Framework (CSF)

### 1. **Identify**
- Conduct regular audits of internal networks, systems, devices, and access privileges to pinpoint security gaps.
- Inventory systems, processes, and data assets requiring protection.

### 2. **Protect**
- Implement firewall rules to limit ICMP traffic rates.
- Enforce policies and provide training to staff to recognize DDoS attack patterns.
- Deploy advanced security tools like IDS/IPS for proactive defense.

### 3. **Detect**
- Use network monitoring tools to scan for traffic anomalies.
- Deploy a Security Information and Event Management (SIEM) system for real-time event detection.

### 4. **Respond**
- Develop and communicate an action plan for future DDoS attacks.
- Analyze network logs to understand attack vectors and patterns.
- Isolate affected systems to prevent further damage.

### 5. **Recover**
- Restore critical systems and services first.
- Implement procedures for blocking external ICMP flood attacks at the firewall level.
- Conduct post-incident reviews to improve recovery strategies.

---

## Summary of Recommendations
| **Function**   | **Description**                                                                                                                                  | **Key Activities**                                                                                                                                                                                                                                                                                   |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Identify**    | Create an inventory of organizational systems, processes, assets, data, people, and capabilities that need to be secured.                      | - **Technology/Asset Management**: Identify affected hardware devices, operating systems, and software; trace the flow of the attack through the internal network.  <br> - **Process/Business Environment**: Determine which business processes were affected. <br> - **People**: Identify necessary access to affected systems. |
| **Protect**     | Develop and implement safeguards to protect the identified items and ensure delivery of services.                                               | - **Access Control**: Limit access to critical items and block non-trusted sources. <br> - **Awareness/Training**: Educate staff on preventing similar attacks. <br> - **Data Security**: Enhance the security of affected data. <br> - **Information Protection/Procedures**: Update and implement protection procedures. <br> - **Maintenance**: Update affected hardware, operating systems, or software. <br> - **Protective Technology**: Implement technologies like firewalls or IPS. |
| **Detect**      | Design and implement a system with tools needed for detecting threats and attacks.                                                              | - **Anomalies and Events**: Use tools like SIEM to detect anomalies and alert IT staff. <br> - **Continuous Monitoring**: Implement monitoring tools to track network activity. <br> - **Detection Process**: Use IDS tools to detect security events.                                                                                      |
| **Respond**     | Design action plans for responding to threats and attacks.                                                                                      | - **Response Planning**: Develop future action plans. <br> - **Communications**: Plan how to communicate security responses internally and externally. <br> - **Analysis**: Determine analysis steps for future attacks. <br> - **Mitigation**: Define steps to isolate or neutralize affected resources. <br> - **Improvements**: Enhance future response strategies.                                          |
| **Recover**     | Construct a plan and implement the framework for recovering and restoring affected systems and/or data.                                         | - **Recovery Planning**: Outline steps to restore resources. <br> - **Improvements**: Identify updates needed for recovery systems or processes. <br> - **Communications**: Communicate restoration procedures internally and to end users.                                                                                                |
