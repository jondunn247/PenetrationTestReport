# PenetrationTestReport
Conducted a penetration test by attacking a fictional organization's web application, Linux servers, and Windows servers.

<h2>Utilities Used</h2>

- <b>Linux Servers</b> 
- <b>Microsoft Servers</b>
  
<h2>Environments Used </h2>

- <b>Azure Labs</b>

# Rekall Corporation


# Penetration Test Report

**<span style="text-decoration:underline;">Student Note</span>: Complete all sections highlighted in yellow.**


# 


## Confidentiality Statement

This document contains confidential and privileged information from Rekall Inc. (henceforth known as Rekall). The information contained in this document is confidential and may constitute inside or non-public information under international, federal, or state laws. Unauthorized forwarding, printing, copying, distribution, or use of such information is strictly prohibited and may be unlawful. If you are not the intended recipient, be aware that any disclosure, copying, or distribution of this document or its parts is prohibited.

## Table of Contents

#### Confidentiality Statement	2

#### Contact Information	4

#### Document History	4

#### Introduction	5

#### Assessment Objective	5

#### Penetration Testing Methodology	6

#### Reconnaissance	6

#### Identification of Vulnerabilities and Services	6

#### Vulnerability Exploitation	6

#### Reporting	6

#### Scope	7

#### Executive Summary of Findings	8

#### Grading Methodology	8

#### Summary of Strengths	9

#### Summary of Weaknesses	9

#### Executive Summary Narrative	10

#### Summary Vulnerability Overview	13

#### Vulnerability Findings	14

# 


## Contact Information


<table>
  <tr>
   <td><strong>Company Name</strong>
   </td>
   <td>Swish Corp
   </td>
  </tr>
  <tr>
   <td><strong>Contact Name</strong>
   </td>
   <td>Jonathan Dunn
   </td>
  </tr>
  <tr>
   <td><strong>Contact Title</strong>
   </td>
   <td>Pen Tester
   </td>
  </tr>
</table>



## Document History


<table>
  <tr>
   <td><strong>Version</strong>
   </td>
   <td><strong>Date</strong>
   </td>
   <td><strong>Author(s)</strong>
   </td>
   <td><strong>Comments</strong>
   </td>
  </tr>
  <tr>
   <td>001
   </td>
   <td>07-02-2023
   </td>
   <td>Jonathan Dunn
   </td>
   <td>
   </td>
  </tr>
</table>



# 


## Introduction

In accordance with Rekall policies, our organization conducts external and internal penetration tests of its networks and systems throughout the year. The purpose of this engagement was to assess the networks’ and systems’ security and identify potential security flaws by utilizing industry-accepted testing methodology and best practices.

For the testing, we focused on the following:



* Attempting to determine what system-level vulnerabilities could be discovered and exploited with no prior knowledge of the environment or notification to administrators.
* Attempting to exploit vulnerabilities found and access confidential information that may be stored on systems.
* Documenting and reporting on all findings.

All tests took into consideration the actual business processes implemented by the systems and their potential threats; therefore, the results of this assessment reflect a realistic picture of the actual exposure levels to online hackers. This document contains the results of that assessment.


### Assessment Objective

The primary goal of this assessment was to provide an analysis of security flaws present in Rekall’s web applications, networks, and systems. This assessment was conducted to identify exploitable vulnerabilities and provide actionable recommendations on how to remediate the vulnerabilities to provide a greater level of security for the environment.

We used our proven vulnerability testing methodology to assess all relevant web applications, networks, and systems in scope. 

Rekall has outlined the following objectives:

Table 1: Defined Objectives


<table>
  <tr>
   <td><strong>Objective</strong>
   </td>
  </tr>
  <tr>
   <td>Find and exfiltrate any sensitive information within the domain.
   </td>
  </tr>
  <tr>
   <td>Escalate privileges.
   </td>
  </tr>
  <tr>
   <td>Compromise several machines.
   </td>
  </tr>
</table>



# 


## Penetration Testing Methodology


### Reconnaissance

We begin assessments by checking for any passive (open source) data that may assist the assessors with their tasks. If internal, the assessment team will perform active recon using tools such as Nmap and Bloodhound.


### Identification of Vulnerabilities and Services

We use custom, private, and public tools such as Metasploit, hashcat, and Nmap to gain perspective of the network security from a hacker’s point of view. These methods provide Rekall with an understanding of the risks that threaten its information, and also the strengths and weaknesses of the current controls protecting those systems. The results were achieved by mapping the network architecture, identifying hosts and services, enumerating network and system-level vulnerabilities, attempting to discover unexpected hosts within the environment, and eliminating false positives that might have arisen from scanning. 


### Vulnerability Exploitation

Our normal process is to both manually test each identified vulnerability and use automated tools to exploit these issues. Exploitation of a vulnerability is defined as any action we perform that gives us unauthorized access to the system or the sensitive data. 


### Reporting

Once exploitation is completed and the assessors have completed their objectives, or have done everything possible within the allotted time, the assessment team writes the report, which is the final deliverable to the customer.


# 


## Scope

Prior to any assessment activities, Rekall and the assessment team will identify targeted systems with a defined range or list of network IP addresses. The assessment team will work directly with the Rekall POC to determine which network ranges are in-scope for the scheduled assessment. 

It is Rekall’s responsibility to ensure that IP addresses identified as in-scope are actually controlled by Rekall and are hosted in Rekall-owned facilities (i.e., are not hosted by an external organization). In-scope and excluded IP addresses and ranges are listed below. 


# 


## Executive Summary of Findings


### Grading Methodology

Each finding was classified according to its severity, reflecting the risk each such vulnerability may pose to the business processes implemented by the application, based on the following criteria:

**Critical**:	 Immediate threat to key business processes.

**High**:		 Indirect threat to key business processes/threat to secondary business processes.

**Medium**:	 Indirect or partial threat to business processes. 

**Low**:		 No direct threat exists; vulnerability may be leveraged with other vulnerabilities.

Informational:    No threat; however, it is data that may be used in a future attack.

As the following grid shows, each threat is assessed in terms of both its potential impact on the business and the likelihood of exploitation:



<img align="middle" src="https://i.imgur.com/e4ZxCWj.png" height="60%" width="60%"/>


### 


### Summary of Strengths

While the assessment team was successful in finding several vulnerabilities, the team also recognized several strengths within Rekall’s environment. These positives highlight the effective countermeasures and defenses that successfully prevented, detected, or denied an attack technique or tactic from occurring. 



* Hackers cannot access the root or administration user's system because sudo privileges aren't available, and staff aren't opening phishing emails.
* Exploitation details
* To prevent unauthorized access, tools such as Nmap and Metasploit are used


### Summary of Weaknesses

We successfully found several critical vulnerabilities that should be immediately addressed in order to prevent an adversary from compromising the network. These findings are not specific to a software version but are more general and systemic vulnerabilities.



* Block ports 22 and 80, and 135 
* It is possible for attackers to access user accounts and compromise sensitive information
* There are multiple vulnerabilities in Apache's web server
* The physical address of Rekall is available to the public




## Executive Summary

Found several vulnerabilities during penetration test, some of which could be easily exploited by malicious actors. One key finding from the test was that the company's firewall was vulnerable to being accessed simply from the internet. Additionally, a vulnerability in the company's email server could allow hackers to gain access to confidential information, and another vulnerability in the email server could allow attackers to spoof emails. Rekall Corp. recommends that their security be reviewed and their firewalls be updated as part of this process.

<img align="middle" src="https://i.imgur.com/X4wrzE2.png" height="60%" width="60%"/>


(Nmap scan 192.168.14.35)



<img src="https://i.imgur.com/cD46WbG.png" height="60%" width="60%"/>


 (Leaked Server Info - OWASP Tool - About-Rekall.php)

<img src="https://i.imgur.com/5gil6ld.png" height="60%" width="60%"/>


Metasploit


## 


## Summary Vulnerability Overview


<table>
  <tr>
   <td><strong>Vulnerability</strong>
   </td>
   <td><strong>Severity</strong>
   </td>
  </tr>
  <tr>
   <td>The firewall helps enables access to the network through the internet.
   </td>
   <td><strong>High</strong>
   </td>
  </tr>
  <tr>
   <td>The web server makes it possible for attackers to obtain private data.
   </td>
   <td><strong>Medium</strong>
   </td>
  </tr>
  <tr>
   <td>A weakness in the email server that can allow spoofing of emails by an attacker.
   </td>
   <td><strong>Medium</strong>
   </td>
  </tr>
  <tr>
   <td>FTP port 21 is open
   </td>
   <td><strong>High</strong>
   </td>
  </tr>
  <tr>
   <td>Public Documents and Folder Storing Sensitive Data 
   </td>
   <td><strong>High</strong>
   </td>
  </tr>
  <tr>
   <td>The IP address is visible to Nmap scan
   </td>
   <td><strong>Critical</strong>
   </td>
  </tr>
  <tr>
   <td>SQL Injection
   </td>
   <td><strong>Critical</strong>
   </td>
  </tr>
  <tr>
   <td>Shellshock on Web Server (port 80)
   </td>
   <td><strong>Critical</strong>
   </td>
  </tr>
  <tr>
   <td>Sensitive Data Exposure
   </td>
   <td><strong>Critical</strong>
   </td>
  </tr>
  <tr>
   <td>Linux Privilege Escalation 
   </td>
   <td><strong>Critical</strong>
   </td>
  </tr>
  <tr>
   <td>User Credential Exposure 
   </td>
   <td><strong>Critical</strong>
   </td>
  </tr>
  <tr>
   <td>Open Source Exposed Data
   </td>
   <td><strong>High</strong>
   </td>
  </tr>
  <tr>
   <td>Tomcat Remote Code Execution Vulnerability 
   </td>
   <td><strong>High</strong>
   </td>
  </tr>
  <tr>
   <td>Port SLMail Exploited Through Metasploit
   </td>
   <td><strong>Critical</strong>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
  </tr>
</table>


The following summary tables represent an overview of the assessment findings for this penetration test:


<table>
  <tr>
   <td><strong>Scan Type</strong>
   </td>
   <td><strong>Total</strong>
   </td>
  </tr>
  <tr>
   <td>Hosts
   </td>
   <td>192.168.14.0/24
<p>
192.168.13.14
<p>
192.168.13.11
<p>
172.22.117.20
<p>
192.168.13.13
   </td>
  </tr>
  <tr>
   <td>Ports
   </td>
   <td>22, 80, 135
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>Exploitation Risk</strong>
   </td>
   <td><strong>Total</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Critical</strong>
   </td>
   <td>14
   </td>
  </tr>
  <tr>
   <td><strong>High</strong>
   </td>
   <td>5
   </td>
  </tr>
  <tr>
   <td><strong>Medium</strong>
   </td>
   <td>3
   </td>
  </tr>
  <tr>
   <td><strong>Low</strong>
   </td>
   <td>0
   </td>
  </tr>
</table>



## Vulnerability Findings


<table>
  <tr>
   <td><strong>Vulnerability 1</strong>
   </td>
   <td><strong>Findings</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Title</strong>
   </td>
   <td>SQL Database Provide Credentials 
   </td>
  </tr>
  <tr>
   <td><strong>Type (Web app / Linux OS / WIndows OS)</strong>
   </td>
   <td>Web App
   </td>
  </tr>
  <tr>
   <td><strong>Risk Rating</strong>
   </td>
   <td>High
   </td>
  </tr>
  <tr>
   <td><strong>Description</strong>
   </td>
   <td>Database startup provided free credentials
   </td>
  </tr>
  <tr>
   <td><strong>Images</strong>
   </td>
   <td>

<img src="https://i.imgur.com/2MPdcZo.png" height="60%" width="60%"/>

   </td>
  </tr>
  <tr>
   <td><strong>Affected Hosts</strong>
   </td>
   <td>192.168.14.35
   </td>
  </tr>
  <tr>
   <td><strong>Remediation</strong>
   </td>
   <td>Update passwords and turn on encryption 
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>Vulnerability 2</strong>
   </td>
   <td><strong>Findings</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Title</strong>
   </td>
   <td>OWASP ZAP
   </td>
  </tr>
  <tr>
   <td><strong>Type (Web app / Linux OS / WIndows OS)</strong>
   </td>
   <td>Linux OS
   </td>
  </tr>
  <tr>
   <td><strong>Risk Rating</strong>
   </td>
   <td>High
   </td>
  </tr>
  <tr>
   <td><strong>Description</strong>
   </td>
   <td>Passive Active Scanning
   </td>
  </tr>
  <tr>
   <td><strong>Images</strong>
   </td>
   <td>


<img src="https://i.imgur.com/qqhmW7y.png" />

  </tr>
  <tr>
   <td><strong>Affected Hosts</strong>
   </td>
   <td>192.168.14.35
   </td>
  </tr>
  <tr>
   <td><strong>Remediation</strong> 
   </td>
   <td>Develop a secure coding practises strategy.
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>Vulnerability 3</strong>
   </td>
   <td><strong>Findings</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Title</strong>
   </td>
   <td> Foxyproxy
   </td>
  </tr>
  <tr>
   <td><strong>Type (Web app / Linux OS / WIndows OS)</strong>
   </td>
   <td>Linux os
   </td>
  </tr>
  <tr>
   <td><strong>Risk Rating</strong>
   </td>
   <td>Medium
   </td>
  </tr>
  <tr>
   <td><strong>Description</strong>
   </td>
   <td>Bypassing Internet Censorship
   </td>
  </tr>
  <tr>
   <td><strong>Images</strong>
   </td>
   <td>

<img src="https://i.imgur.com/oRo3dux.png" />

   </td>
  </tr>
  <tr>
   <td><strong>Affected Hosts</strong>
   </td>
   <td>127.0.0.1
   </td>
  </tr>
  <tr>
   <td><strong>Remediation</strong> 
   </td>
   <td>Check the proxy servers. Take care with sensitive information.
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>Vulnerability 4</strong>
   </td>
   <td><strong>Findings</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Title</strong>
   </td>
   <td>Shellshock
   </td>
  </tr>
  <tr>
   <td><strong>Type (Web app / Linux OS / WIndows OS)</strong>
   </td>
   <td>Linux OS
   </td>
  </tr>
  <tr>
   <td><strong>Risk Rating</strong>
   </td>
   <td>Critical
   </td>
  </tr>
  <tr>
   <td><strong>Description</strong>
   </td>
   <td>Use sudoers and apache to grant root privileges
   </td>
  </tr>
  <tr>
   <td><strong>Images</strong>
   </td>
   <td>

<img src="https://i.imgur.com/hDODXKD.png" />

   </td>
  </tr>
  <tr>
   <td><strong>Affected Hosts</strong>
   </td>
   <td>192.168.13.14
   </td>
  </tr>
  <tr>
   <td><strong>Remediation</strong> 
   </td>
   <td>impose restrictions on all sudo accounts
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>Vulnerability 5</strong>
   </td>
   <td><strong>Findings</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Title</strong>
   </td>
   <td>Meterpreter
   </td>
  </tr>
  <tr>
   <td><strong>Type (Web app / Linux OS / WIndows OS)</strong>
   </td>
   <td>Linux OS
   </td>
  </tr>
  <tr>
   <td><strong>Risk Rating</strong>
   </td>
   <td>Critical
   </td>
  </tr>
  <tr>
   <td><strong>Description</strong>
   </td>
   <td>Payload Exploitation
   </td>
  </tr>
  <tr>
   <td><strong>Images</strong>
   </td>
   <td>

<img src="https://i.imgur.com/cT3tvpi.png" />
<p>


<img src="https://i.imgur.com/NL27FKW.png" />

   </td>
  </tr>
  <tr>
   <td><strong>Affected Hosts</strong>
   </td>
   <td>192.168.13.12
   </td>
  </tr>
  <tr>
   <td><strong>Remediation</strong> 
   </td>
   <td>Use Updates
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>Vulnerability 6</strong>
   </td>
   <td><strong>Findings</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Title</strong>
   </td>
   <td>Certificate Search 
   </td>
  </tr>
  <tr>
   <td><strong>Type (Web app / Linux OS / WIndows OS)</strong>
   </td>
   <td>Web App
   </td>
  </tr>
  <tr>
   <td><strong>Risk Rating</strong>
   </td>
   <td>Medium
   </td>
  </tr>
  <tr>
   <td><strong>Description</strong>
   </td>
   <td>Rekall Search on crt.sh
   </td>
  </tr>
  <tr>
   <td><strong>Images</strong>
   </td>
   <td>

<img src="https://i.imgur.com/0ylbnJR.png" />

   </td>
  </tr>
  <tr>
   <td><strong>Affected Hosts</strong>
   </td>
   <td>34.102.136.180
   </td>
  </tr>
  <tr>
   <td><strong>Remediation</strong> 
   </td>
   <td>Accessible information on the crt.sh website, thus preventing information from being exposed to the site would be necessary to address the issue.
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>Vulnerability 7</strong>
   </td>
   <td><strong>Findings</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Title</strong>
   </td>
   <td>Nmap Scan Results
   </td>
  </tr>
  <tr>
   <td><strong>Type (Web app / Linux OS / WIndows OS)</strong>
   </td>
   <td>Linux OS
   </td>
  </tr>
  <tr>
   <td><strong>Risk Rating</strong>
   </td>
   <td>Critical
   </td>
  </tr>
  <tr>
   <td><strong>Description</strong>
   </td>
   <td>Nmap scan 192.168.14.35 
   </td>
  </tr>
  <tr>
   <td><strong>Images</strong>
   </td>
   <td>

<img src="https://i.imgur.com/sgLYlgn.png" />

   </td>
  </tr>
  <tr>
   <td><strong>Affected Hosts</strong>
   </td>
   <td>192.168.14.35
   </td>
  </tr>
  <tr>
   <td><strong>Remediation</strong> 
   </td>
   <td>For unauthorized users, IP blocking
   </td>
  </tr>
</table>


We also discovered the following additional vulnerabilities in addition to the ones mentioned above;



* Leaked server information


<img src="https://i.imgur.com/qaWq8V5.png" />



* Simple password cracking

<img src="https://i.imgur.com/6qicIvc.png" />


* Multiple usernames were retrieved 


<img src="https://i.imgur.com/RPU91Kj.png" />



* There is no coded output.



<img src="https://i.imgur.com/iVrSUTn.png" />



* There is no coded output



<img src="https://i.imgur.com/7DYKkNX.png" />
