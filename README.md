# Phishing Analysis Report
**Incident ID:** #001-Phish-111  
**Date:**        --/--/----
## 

> **<ins>Source:</ins>**
> https://challenges.malwarecube.com/#/c/074e4448-e8d7-4122-86f2-36a4d7b2a18b  
> **<ins>Question:</ins>**
><picture>![image](https://github.com/user-attachments/assets/1b7ae777-6107-499e-9173-9e4ac23e4a0a) </picture>

> ### Architecture
> <picture>![image](https://github.com/user-attachments/assets/2625168d-f29c-4582-b83f-756a89fb21d8) </picture>


## Description

User Dana Derringer was sent a mail she claimed to be suspecious which warrants further investigation.
The content of the email was for Dana to take an action with regards to an unusual activity on the account, on which her account is purported to be disabled and asked to reactivate by clicking on a link.
Dana has forwarded the email to the security team for further investigation.

## Procedure - Phishing Analysis Report:

**1. Command to Accessing the file in question** 
![image](https://github.com/user-attachments/assets/26dc0bd7-ceff-4253-aace-fc4530c4e431)

**2. Command to get the hash of the file to record its integrity check.**
![image](https://github.com/user-attachments/assets/07faf62d-e99c-4d0d-930c-3c3ce85d4597)

**3. Opening to read the content of the file in a virtual environment with Mozila Thunderbird**
![image](https://github.com/user-attachments/assets/282acf76-dff9-4486-8317-a6da0f710bf8)
![image](https://github.com/user-attachments/assets/de978603-2c70-4c8e-8d63-16850a545d59)

**4. Using the 'eioc.py script to extract the various components of the email file** 
![image](https://github.com/user-attachments/assets/2a2923b5-db5f-43c9-a02a-73a2ebf95e81)

**5. Checking various components/ parts of the email as below:**

**Header**

**<ins>Date:</ins>** Tue, 31 Oct 2023 10:10:04 -0900
**<ins>Subject:</ins>** Your account has been flagged for unusual activity

**<ins>From:</ins>** social201511138@social.helwan.edu.eg  
**<ins>To:</ins>**   dderringer@mighty-solutions.net

**<ins>Reply-To:</ins>** -  
**<ins>Return-Path:</ins>** social201511138@social.helwan.edu.eg

**<ins>Sender IP:</ins>**  
![image](https://github.com/user-attachments/assets/83a30b9d-5827-4304-b309-1fb1cc13de98)

**<ins>Resolve Host:<ins>** mail-am6eur05on2060.outbound.protection.outlook.com
![image](https://github.com/user-attachments/assets/33c71829-6e1c-4a6f-8e0c-d137d70f2980)


**<ins>Message-ID:</ins>** JMrByPl2c3HBo8SctKnJ5C5Gp64sPSSWk76p4sjQ@s6

**<ins>URLs</ins>**
hxxps[://]raw[.]githubusercontent[.]com/MalwareCube/SOC101/main/assets/01_Phishing_Analysis/microsoft[.]jpg
hxxps[://]0[.]232[.]205[.]92[.]host[.]secureserver[.]net/lclbluewin08812/


**<ins>Attachments</ins>**

No attachment

## Artifact Analysis

**<ins>Sender Analysis:</ins>**
Sender claims to be from Microsoft but the email ID proves false. THe domain name is 'social.helwan.edu.eg'. The information obtained on it is below:
https://whois.domaintools.com/helwan.edu.eg
![image](https://github.com/user-attachments/assets/8883c5c1-31d7-4b86-8795-f7c83e60c97f)


**<ins>URL Analysis:</ins>**
The URLs obtained were originally in thier defang state. To get the fang state for clearitiy and readability, I used the cybersheff tool - URL: https://gchq.github.io/CyberChef/  

**<ins>URLs: Converting it using the fang operator produced the URL as: </ins>**
1. https://raw.githubusercontent.com/MalwareCube/SOC101/main/assets/01_Phishing_Analysis/microsoft.jpg
2. https://0.232.205.92.host.secureserver.net/lclbluewin08812/  

All the URL was flagged as malicious when placed in the Virustotal engine: -by 1 and 8 security vendors respectively as seen in the image below.
1. site:     https://www.virustotal.com/gui/url/a8f90df07430e714681833c6c1d45b68a58095b9540dc8dbd7e87b92cd8f0094  
   Snapshot: ![image](https://github.com/user-attachments/assets/227ffb34-37b9-49a9-b327-17c6e86e4357)
2. site: https://www.virustotal.com/gui/url/6a4ea48b89905818a22b0dbfdd6c9402cfe321998a530f105f60d7d8d0fc62ef  
   Snapshot: ![image](https://github.com/user-attachments/assets/04101e01-8c25-449a-be29-759beb30f1a1)


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
