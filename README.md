# Phishing Analysis 

> **<ins>Source:</ins>**
> https://challenges.malwarecube.com/#/c/074e4448-e8d7-4122-86f2-36a4d7b2a18b  
> **<ins>Question:</ins>**
><picture>![image](https://github.com/user-attachments/assets/1b7ae777-6107-499e-9173-9e4ac23e4a0a) </picture>

> ### Architecture
> <picture>![image](https://github.com/user-attachments/assets/2625168d-f29c-4582-b83f-756a89fb21d8) </picture>

## Procedure
**1. Command to Accessing the file in question** 
<picture>![image](https://github.com/user-attachments/assets/26dc0bd7-ceff-4253-aace-fc4530c4e431) </picture>

**2. Command to get the hash of the file to record its integrity check.**
<picture>![image](https://github.com/user-attachments/assets/07faf62d-e99c-4d0d-930c-3c3ce85d4597)</picture>

**3. Opening to read the content of the file in a virtual environment with Mozila Thunderbird**
<picture>![image](https://github.com/user-attachments/assets/282acf76-dff9-4486-8317-a6da0f710bf8)</picture>
<picture>![image](https://github.com/user-attachments/assets/de978603-2c70-4c8e-8d63-16850a545d59)</picture>

**4. Using the 'eioc.py script to extract the various components of the email file** 
<picture>![image](https://github.com/user-attachments/assets/2a2923b5-db5f-43c9-a02a-73a2ebf95e81)</picture>

# 
## Report

**Incident ID:** #001-Phish-111  
**Date:**        --/--/----
## 


## Executive Summary

A suspicious email was reported by Dana Derringer (dderringer@mighty-solutions.net) claiming her account was disabled. Email was forwarded to Comany's security team for investigation. Analysis confirms the email is a phishing attempt. Key findings include:
+ Sender impersonation: Content of email appears to be from "Microsoft" but doamin email is identified as social.helwan.edu.eg.
+ Malicious URLs: Attached email and image Links flagged by VirusTotal.

## Technical Analysis

a. Email Metadata

|Field | Value  | 
|---------| --------- |
| Date | Tue, 31 Oct 2023 10:10:04 -0900 |
| Subject | Your account has been flagged for unusual activity | 
| From | social201511138@social.helwan.edu.eg |
| To | dderringer@mighty-solutions.net |
| Reply-To |(Empty) |
| Return-Path| social201511138@social.helwan.edu.eg |
| Sender IP| <picture>![image](https://github.com/user-attachments/assets/83a30b9d-5827-4304-b309-1fb1cc13de98)</picture> |
| Resolve Host| mail-am6eur05on2060.outbound.protection.outlook.com\ <picture>![image](https://github.com/user-attachments/assets/33c71829-6e1c-4a6f-8e0c-d137d70f2980)</picture> |
| Message-ID | JMrByPl2c3HBo8SctKnJ5C5Gp64sPSSWk76p4sjQ@s6 |  

b. Associated URLs
+  Defang - Orignial state
    
| Logo | Email content link |
|---------| --------- |
| hxxps[://]raw[.]githubusercontent[.]com/MalwareCube/SOC101/main/assets/01_Phishing_Analysis/microsoft[.]jpg | hxxps[://]0[.]232[.]205[.]92[.]host[.]secureserver[.]net/lclbluewin08812/ |

+ Deobsfuscate State
    
Using the Cyberchef tool: https://gchq.github.io/CyberChef/ 
  | Logo | Email content link | 
|---------| --------- |
|[ hxxps[://]raw[.]githubusercontent[.]com/MalwareCube/SOC101/main/assets/01_Phishing_Analysis/microsoft[.]jpg](https://raw.githubusercontent.com/MalwareCube/SOC101/main/assets/01_Phishing_Analysis/microsoft.jpg) | https://0.232.205.92.host.secureserver.net/lclbluewin08812/ |

URL were flagged as malicious in the Virustotal engine:  
a. [1/90 vendors flagged as malicious] site:     https://www.virustotal.com/gui/url/a8f90df07430e714681833c6c1d45b68a58095b9540dc8dbd7e87b92cd8f0094  
   + Snapshot: ![image](https://github.com/user-attachments/assets/227ffb34-37b9-49a9-b327-17c6e86e4357)
b. [8/90 flagged as malicious] site: https://www.virustotal.com/gui/url/6a4ea48b89905818a22b0dbfdd6c9402cfe321998a530f105f60d7d8d0fc62ef  
  + Snapshot: ![image](https://github.com/user-attachments/assets/04101e01-8c25-449a-be29-759beb30f1a1)
\
+ Sender Email Analysis
   \
Email proves to be valid. It was checked from different sources as indicated in the table below.
|Source 1 | Source 2  | Source 3 |
|---------| --------- | -------- |
| https://debounce.io/| https://www.spokeo.com/ | https://www.verifyemailaddress.org/email-validation |
|<picture>![image](https://github.com/user-attachments/assets/3eb72df2-046b-4c87-80d3-6974f0683dff) </picture> | <picture>![image](https://github.com/user-attachments/assets/38c5489d-edde-489b-afc6-df3a2ecb6e15)</picture> | <picture>![image](https://github.com/user-attachments/assets/d6fb8f53-0921-4045-99b1-ae422db02999) </picture> |

+ Metadata Aanalysis
  \
  
| Field        | Value                                       | Analysis                                |
|--------------|---------------------------------------------|-----------------------------------------|
| **From**     | `social201511138@_social.helwan.edu.eg_` | Domain unrelated to Microsoft.\ https://whois.domaintools.com/helwan.edu.eg\ <picture>![image](https://github.com/user-attachments/assets/8883c5c1-31d7-4b86-8795-f7c83e60c97f </picture>  |
| **Reply-To** | *(Empty)*                                   |        |
| **Sender IP**| `40.107.22.60` (`mail-am6eur05on2060.outbound.protection.outlook.com`) | Spoofed Microsoft infrastructure.      |
| **Message ID**| `MrByPl2c3HBo8SctKnj5C5Gp64spSSWx76p4sJQ@s6` | Non-standard formatting (likely forged). |





**<ins>IP Analysis:</ins>**

10[.]152[.]26[.]146 -> This is a private IP address  
https://whois.domaintools.com/10.152.26.146

40[.]107[.]22[.]60  
https://whois.domaintools.com/40.107.22.60

0[.]232[.]205[.]92

## Verdict

Virus total has proven that the link associated with the email is a Phishing link. The attached image includes a URL which is also malicious as seen in the snapshot in the Analysis above.
Per the information indicated in the analysis section, it can be said that the email is a phishing email.

Defense Actions
======================================
Block access to the domain names of the link.
Educate users to be aware of such phishing emails.
