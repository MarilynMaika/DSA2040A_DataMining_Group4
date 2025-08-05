# Power BI Dashboard

**Rita**

## Overview

This interactive Power BI dashboard offers in-depth insights into cybersecurity session data to support intrusion detection and threat analysis. It is organized into two main pages:



### Page 1: Risk & Threat Analytics

Focuses on identifying high-risk sessions and patterns that signal suspicious behavior.

**Key Visuals:**
- **Attack vs. Non-Attack Sessions:** Donut chart showing the percentage of sessions flagged as attacks vs. safe ones for quick risk assessment.
- **Top 20 Risky Sessions Table:** Tabular view ranking sessions by attack detection, failed login attempts, IP reputation scores and unusual activity.
- **Failed Logins by Browser:** Highlights browsers (e.g., Chrome, Firefox) with the most failed login attempts, helping identify potential vulnerabilities by client type.
- **Top 10 Longest Sessions:** Bar chart showing sessions with the longest durations potentially indicating stealthy, slow-moving attacks.
- **KPIs:** Quick metrics summarizing average attack percentage, average IP reputation score and failed login attempts across sessions.



### Page 2: Cybersecurity Session Overview

Provides a broader view of all network sessions to spot attack trends across encryption, protocols and browser usage.

**Key Visuals:**
- **Sessions by Encryption Type:** Bar chart showing session counts across AES, DES and unsecured (None) encryption methods.
- **Unusual Time Access:** Donut chart illustrating how many sessions occurred at uncommon hours, indicating possible unauthorized access attempts.
- **Protocol Type Distribution:** Distribution of sessions using TCP, UDP and ICMP protocols useful for protocol-level threat analysis.
- **Browser vs Attack:** Visual correlation of browser types with attack likelihood to assess risk exposure by client technology.
- **Top 10 Sessions by Network Packet Size:** Table showing sessions with the largest packet sizes, along with associated browser and protocol types.
- **KPIs:** Quick metrics showing total sessions, attack sessions and average session duration.

**Filters/Slicers:**
- Interactive protocol type filter (TCP, UDP, ICMP) for drilling down into session behavior by network protocol.


## View the Dashboard

https://app.powerbi.com/view?r=eyJrIjoiMTdmNDA5YTQtODM2Yy00ZDNkLWI2OWEtMWI0MjMyMmFiOTZiIiwidCI6IjE2ZDgzZWU2LTI1NGEtNDY5ZC1hNmNjLTU0ZTJjYTIzMTNlNyIsImMiOjh9


