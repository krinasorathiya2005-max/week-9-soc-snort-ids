# Week 9 – SOC Introduction & Snort IDS

## Cyber Security Internship | DG Interns Hub

### Project Overview

Week 9 focuses on understanding Security Operations Center (SOC) concepts and building a basic network monitoring environment using Ubuntu Server and Snort IDS.

The practical work connects SOC theory with a controlled detection exercise by installing Snort, creating custom ICMP and HTTP detection rules, generating authorized traffic, and validating Snort alerts.

---

## Objectives

- Understand what a Security Operations Center (SOC) is.
- Understand L1, L2, and L3 SOC analyst responsibilities.
- Differentiate between SIEM, IDS, and IPS.
- Create an Ubuntu Server virtual environment.
- Perform basic system, hostname, and network configuration.
- Install and verify Snort IDS.
- Understand the structure of Snort rules.
- Create custom ICMP and HTTP detection rules.
- Generate controlled traffic.
- Validate Snort alerts.
- Document practical evidence and results.

---

## Lab Environment

| Component | Purpose |
|---|---|
| Ubuntu Server | Snort monitoring sensor |
| Snort IDS | Network traffic detection |
| Test Machine | Generates authorized test traffic |
| Virtual Network | Provides communication between systems |
| Custom Rules | Detect ICMP and HTTP traffic |
| Terminal | Configuration and alert validation |

---

## SOC Workflow

```text
Monitor → Detect → Triage → Investigate → Respond/Escalate → Document → Improve
SIEM vs IDS vs IPS
Technology	Purpose
SIEM	Collects and correlates logs and security events
IDS	Detects suspicious network activity and generates alerts
IPS	Detects suspicious activity and can actively block/prevent it


Simple Memory Aid
SIEM = Collect & Correlate
IDS  = Detect & Alert
IPS  = Detect & Prevent

Technologies Used
- Ubuntu Server
- Snort IDS
- Linux Terminal
- ICMP / Ping
- HTTP
- Python HTTP Server
- curl
Snort Installation
Snort was installed using:
sudo apt install snort -y

Verify Snort:
snort -V

Test the Snort configuration:
sudo snort -T -c /etc/snort/snort.conf

Snort Rule Structure
action protocol source_ip source_port -> destination_ip destination_port (options)

Example:
alert icmp any any -> any any (msg:"WEEK9 ICMP Ping Detected"; sid:1000001; rev:1;)

Rule Components
Element	Meaning
alert	Action performed when traffic matches
icmp	Protocol being monitored
any	Any source/destination address or port
->	Traffic direction
msg	Alert message
sid	Snort rule identifier
rev	Rule revision


Custom ICMP Detection
The ICMP rule detects ICMP traffic:
alert icmp any any -> any any (msg:"WEEK9 ICMP Ping Detected"; sid:1000001; rev:1;)

Controlled ping traffic was generated from the authorized test machine and the Snort console was checked for the corresponding alert.
Custom HTTP Detection
For HTTP testing, the Snort rule was configured according to the actual test port.
Example using port 8080:
alert tcp any any -> any 8080 (msg:"WEEK9 HTTP Traffic Detected"; sid:1000002; rev:2;)

Start the local HTTP server:
python3 -m http.server 8080

Generate HTTP traffic:
curl http://<TEST-SERVER-IP>:8080/

The Snort console was then checked for the HTTP detection alert.
Snort Monitoring
sudo snort -A console -q -c /etc/snort/snort.conf -i <INTERFACE>

Replace <INTERFACE> with the actual network interface used by the Ubuntu Server.
Repository Structure
week-9-soc-snort-ids/
│
├── README.md
│
├── Report/
│   └── Week_9_SOC_Snort_15_Page_Report.pdf
│
├── PPT/
│   └── Week_9_SOC_Snort_Presentation.pdf
│
├── Screenshots/
│   ├── 01_Ubuntu_Setup/
│   ├── 02_Snort_Installation/
│   ├── 03_Snort_Configuration/
│   ├── 04_Custom_Rules/
│   ├── 05_ICMP_Testing/
│   ├── 06_HTTP_Testing/
│   └── 07_Final_Alerts/
│
├── Rules/
│   └── local.rules
│
└── Evidence/
    └── Testing_Notes.md

Evidence
The project includes practical evidence for:
- Ubuntu Server setup
- Hostname configuration
- Network interface information
- Routing information
- Connectivity testing
- Snort installation
- Snort version verification
- Snort configuration validation
- Custom ICMP rule
- Custom HTTP rule
- Local rules inclusion
- ICMP traffic generation
- ICMP alert
- HTTP server
- HTTP request
- HTTP alert
- Final Snort alert output
All screenshots represent the authorized lab environment.
Troubleshooting
No Traffic Observed
Check the network interface:
ip addr

Check routing:
ip route

Confirm that the traffic is crossing the interface monitored by Snort.
No ICMP Alert
Check:
- local.rules
- Snort configuration
- Rule inclusion
- Monitored interface
- Snort configuration test
sudo snort -T -c /etc/snort/snort.conf

No HTTP Alert
Make sure the HTTP rule matches the actual destination port used by the test server.
For example, if the HTTP server runs on port 8080, the Snort rule must also target port 8080.
Debugging Sequence
Network Connectivity
        ↓
Correct Interface
        ↓
Snort Configuration
        ↓
Rule Inclusion
        ↓
Traffic Generation
        ↓
Alert Output

Learning Outcomes
Through this project, I learned:
- SOC fundamentals
- L1, L2, and L3 SOC responsibilities
- Difference between SIEM, IDS, and IPS
- Ubuntu Server configuration
- Snort IDS installation
- Snort configuration validation
- Snort rule structure
- Custom ICMP detection
- Custom HTTP detection
- Controlled traffic generation
- Alert validation
- Basic troubleshooting
- Security monitoring evidence documentation
Key Takeaway
The main learning from this project was that using a security monitoring tool is only one part of SOC work. A SOC analyst must understand why an alert was generated, what traffic caused it, which rule matched, and how to validate and document the event.
Ethical Disclaimer
All testing was performed only on systems, virtual machines, and network traffic that were owned by the learner or explicitly authorized for testing.
The purpose of this project is defensive monitoring and detection validation. No unauthorized third-party systems or networks were tested.
Project Deliverables
- Week 9 SOC & Snort Report
- Week 9 Presentation
- Snort Custom Rules
- Practical Screenshots
- ICMP Detection Evidence
- HTTP Detection Evidence
- Final Alert Validation
Author
Name: Krina Sorathiya
Internship Domain: Cybersecurity Intern
Organization: DG Interns Hub
References
- OWASP Top 10
- OWASP Web Security Testing Guide
- Snort Documentation
- DG Interns Hub Week 9 Practical Assignment
*Week 9 – SOC Introduction & Snort IDS*
Cyber Security Internship | DG Interns Hub
