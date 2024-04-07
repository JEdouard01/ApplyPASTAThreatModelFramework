<h1>Apply the PASA Threat Model Framework</h1>

<h2>Description</h2>
Project consists of performing a threat model using the PASTA framework for an athletic apparel and shoe company which is getting ready to launch its first mobile application.
<br />

<h2>PASTA</h2>
The Process of Attack Simulation and Threat Analysis (PASTA) is a risk-centric threat modeling process developed by two OWASP leaders and supported by a cybersecurity firm called VerSprite. It focuses primarily on discovering evidence of viable threats and representing this information as a model. The evidence-based design of PASTA can be applied when threat modeling an application or the environment that supports that application. Its seven-stage process consists of various activities that incorporate relevant security artifacts of the environment, like vulnerability assessment reports.


<h2>Stage I: Define business and security objectives</h2>
All shopping applications need to process payments. As such, certain technologies are required to keep information private and secure as well as be in compliant with PCI-DSS. Accordingly, the DevSecOps team will have to analyze the following requirements: 

- <b>Users can create member profiles internally or by connecting external accounts.</b>
- <b>The app must process financial transactions.</b>
- <b>The app should be in compliance with PCI-DSS.</b>

<h2>Stage II: Define the technical scope</h2>
At this stage, the objective is to understand the attack surface by identifying the technologies being used by the application and understanding their dependencies. 


<h3>The technologies being used by the application are the following:</h3> 

- <b>Application programming interface (API)</b>
- <b>Public key infrastructure (PKI)</b>
- <b>SHA-256</b>
- <b>SQL</b>

APIs facilitate the exchange of data between customers, partners, and employees, so they should be prioritized. They handle a lot of sensitive data while they connect various users and systems together. However, details such as which APIs are being used should be considered before prioritizing one technology over another. So, they can be more prone to security vulnerabilities because there’s a larger attack surface.

<h2>Stage III: Decompose the application</h2>

Stage three builds upon the previous stage by investigating how the application's components communicate together. The objective here is to review how the application works and how security controls are currently implemented. This can be illustrated by the use of a data flow diagram that shows how a typical search request passes through multiple layers. One thing you might review here would be to ensure the MySQL database is using prepared statements when queries are input.

<p align="center">
Sample data flow diagram: <br/>
<img src="https://imgur.com/ZjihJ5f.png"/><br />

<h2>Stage IV: Threat analysis</h2>
The primary objective of this stage is to consider the types of threats that might affect the company's mobile application such as:

- <b>Injection</b>
- <b>Session hijacking</b>

Injection attacks are common for SQL databases. Session hijacking is also possible because the mobile application communicates cookies between multiple layers. It's important to consider the technological attack surface and any relevant threats in order to effectively implement one's information security responsibilities.

<h2>Stage V: Vulnerability analysis</h2>

The objective here is to identify what is wrong with the design of the mobile application or its codebase based on one's security testing. 2 vulnerabilities that can be exploited are: 

- <b>Lack of prepared statements</b>
- <b>Broken API token</b>

As previously mentioned, a lack of prepared statements can make the SQL database vulnerable to injection attacks. And session hijacking is possible if cookies are mishandled between input and output sources.

<h2>Stage VI: Attack modeling</h2>

In this stage, the objective is to link the threats and vulnerabilities identified in the previous steps using attack trees in order to illustrate the potential threats that have been identified are actually viable.  

<p align="center">
Sample attack tree diagram: <br/>
<img src="https://imgur.com/bqwNdod.png"/><br />

This sample attack tree models how user data is vulnerable to the attacks that were identified earlier. Like the sample data flow diagram, an actual attack tree for a mobile application would be much more complex than this.

<h2>Stage VII: Risk analysis and impact</h2>

The objective of the final stage of PASTA is to identify ways to mitigate the risks that were identified from stages IV - VI and plan for any remaining risks that can't be remediated. For instance, SHA-256, incident response procedures, password policy, and principle of least privilege are a few examples of technical, operational, and managerial controls that can be implemented before the launch of the mobile application to reduce risk.


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
