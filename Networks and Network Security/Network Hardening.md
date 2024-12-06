Scenario

You are a security analyst working for a social media organization. The organization recently experienced a major data breach, which compromised the safety of their customers’ personal information, such as names and addresses. Your organization wants to implement strong network hardening practices that can be performed consistently to prevent attacks and breaches in the future. 

After inspecting the organization’s network, you discover four major vulnerabilities. The four vulnerabilities are as follows:

1. The organization’s employees' share passwords.

2. The admin password for the database is set to the default.

3. The firewalls do not have rules in place to filter traffic coming in and out of the network.

4. Multifactor authentication (MFA) is not used. 

If no action is taken to address these vulnerabilities, the organization is at risk of experiencing another data breach or other attacks in the future. 

# Security Risk Assessment Repo

## Part 1: Hardening Tools and Methods

| **Hardening Tool/Method**      | **Description**                                                                                 | **Examples**                           |
|--------------------------------|-----------------------------------------------------------------------------------------------|---------------------------------------|
| Multi-Factor Authentication (MFA) | Requires users to verify their credentials using more than one method before accessing an application. | - Fingerprint scans <br> - ID cards <br> - PIN numbers <br> - Passwords |
| Strong Password Policies       | Sets rules for password complexity, length, and usage to enhance security.                    | - Require longer passwords <br> - Disallow password reuse <br> - Suspend accounts after failed login attempts |
| Firewall Maintenance           | Regularly checks and updates firewall configurations to block potential threats.              | - Update allowed/denied traffic rules <br> - Block suspicious sources <br> - Adjust rules after security events |

---

## Part 2: Recommendations and Benefits

| **Recommendation**             | **Benefits**                                                                                  |
|--------------------------------|-----------------------------------------------------------------------------------------------|
| Enforce Multi-Factor Authentication (MFA) | - Adds an additional layer of security. <br> - Reduces success rates of brute force attacks. <br> - Discourages password sharing. |
| Implement Strong Password Policies       | - Prevents malicious access via complex and frequently updated passwords. <br> - Account suspension for failed logins stops brute force attacks. |
| Perform Regular Firewall Maintenance    | - Keeps security rules updated. <br> - Blocks suspicious traffic. <br> - Protects against DoS/DDoS and other attacks. |
