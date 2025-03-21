# Phishing Analysis

Source: https://challenges.malwarecube.com/#/c/074e4448-e8d7-4122-86f2-36a4d7b2a18b  
Question: ![image](https://github.com/user-attachments/assets/1b7ae777-6107-499e-9173-9e4ac23e4a0a)



Solution/ Answer
Phishing Analysis Report:

1. Command to Accessing the file in question: 
![image](https://github.com/user-attachments/assets/26dc0bd7-ceff-4253-aace-fc4530c4e431)

2. Command to get the hash of the file
![image](https://github.com/user-attachments/assets/07faf62d-e99c-4d0d-930c-3c3ce85d4597)

3. Opening to read the content of the file in a virtual environment with Mozila Thunderbird:
![image](https://github.com/user-attachments/assets/282acf76-dff9-4486-8317-a6da0f710bf8)
![image](https://github.com/user-attachments/assets/de978603-2c70-4c8e-8d63-16850a545d59)

4. Using virustotal to check the hash of the file obtained from step 2
There was no flag to it.
   ![image](https://github.com/user-attachments/assets/e1c4b53d-b923-433f-ac13-15ffd4e06242)

Using the 'eioc.py script to extract the various components of the email file: 
![image](https://github.com/user-attachments/assets/2a2923b5-db5f-43c9-a02a-73a2ebf95e81)



Headers
======================================
Date: Tue, 31 Oct 2023 10:10:04 -0900
Subject: Your account has been flagged for unusual activity

To: dderringer@mighty-solutions.net
From: social201511138@social.helwan.edu.eg

Reply-To: No reply to
Return-Path: social201511138@social.helwan.edu.eg

Sender IP: 40.107.22.60
Resolve Host:

Message-ID: JMrByPl2c3HBo8SctKnJ5C5Gp64sPSSWk76p4sjQ@s6


URLs
=======================================
hxxps[://]raw[.]githubusercontent[.]com/MalwareCube/SOC101/main/assets/01_Phishing_Analysis/microsoft[.]jpg
hxxps[://]0[.]232[.]205[.]92[.]host[.]secureserver[.]net/lclbluewin08812/



Attachments
======================================
No attachment


Description
======================================



Artifact Analysis
======================================
Sender Analysis:


URL Analysis:
The URLs obtained were originally in thier defang state. To get the fang state for clearitiy and readability, I used the cybersheff tool - URL: https://gchq.github.io/CyberChef/
URLs: Converting it using the fang operator produced the URL as: 
1. https://raw.githubusercontent.com/MalwareCube/SOC101/main/assets/01_Phishing_Analysis/microsoft.jpg
2. https://0.232.205.92.host.secureserver.net/lclbluewin08812/

All the URL was flagged as malicious when placed in the Virustotal engine: -by 1 and 8 security vendors respectively as seen in the image below.
1. ![Uploading image.png…]()

2. ![Uploading image.png…]()


Verdict
======================================



Defense Actions
======================================

