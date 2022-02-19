# Identifying DDoS Attacks using Classification #
### By: Nate DiRenzo

## Statement of Need:

Distributed Denial of Service attacks are a common form of malicious activity intended to disrupt the flow of normal traffic to a victim server. To accomplish this, DDoS overwhelms the target network/service or its surrounding infrastructure with a flood of Internet traffic.

DDoS attacks are effective because they make use of multiple compromised computer systems as sources of malicious traffic, hence the 'distributed' part of DDoS. These 'bots' or 'zombies' are infected with malware that allows an attacker to control them remotely. These bots are then orchestrated into a 'botnet', and the attacker can direct the attack by programmatically sending instructions to each bot. Compromised devices can include any internet connected device, such as computers and IoT devices, or mundane household items like smart doorbells or lightbulbs.

DDoS attacks are omnipresent in our internet-driven world. [The Digital Attack Map](https://www.digitalattackmap.com/#anim=1&color=0&country=ALL&list=0&time=18763&view=map) provides a live look at active DDoS attacks currently happening globally. Importantly, DDoS attacks are relatively inexpensive to initiate, with some estimates placing the cost of a month-long deployment of a mid-sized DDoS attack at [$311 on the Dark Web](https://www.missioncriticalmagazine.com/articles/93185-the-dark-web-ddos-attacks-sell-for-as-low-as-10-per-hour).

Further, DDoS attacks are directed at a wide variety of organizations. From Internet giants like [Google](https://www.pcmag.com/news/google-says-biggest-ddos-attack-on-record-hit-the-company-in-2017) and [Amazon](https://www.theverge.com/2020/6/18/21295337/amazon-aws-biggest-ddos-attack-ever-2-3-tbps-shield-github-netscout-arbor), to [financial institutions](https://www.wsj.com/articles/hackers-targeted-financial-sector-in-mass-extortion-campaign-11612909155), [gaming companies](https://www.invenglobal.com/articles/15807/ddos-attack-cripples-battlenet), [federal agencies](https://www.vox.com/recode/2020/3/16/21181825/health-human-services-coronavirus-website-ddos-cyber-attack), [journalistic publications](https://www.inverse.com/article/33520-new-york-times-reddit-ddos-attack), and [not for profits](https://www.computerworld.com/article/2495967/update--spamhaus-hit-by-biggest-ever-ddos-attacks.html). [GitHub](https://www.wired.com/story/github-ddos-memcached/) itself has even been subject to DDoS attacks.

It's difficult to quantify the business impact of DDoS attacks. Successful attacks can result in outright downtime or productivity constraints, data breaches, reputational damage, and loss of SEO ranking. Ransom and extortion-based DDoS attacks have also become more prevalent in reent years, meaning businesses are often forced to pay attackers large sums to stop an in-progress attack, in addition to incurring the traditional costs associated with DDoS attacks. 

A [2017 Kaspersky Survey](https://usa.kaspersky.com/about/press-releases/2018_ddos-breach-costs-rise-to-over-2m-for-enterprises-finds-kaspersky-lab-report) estimated the average cost of enduring a DDoS attack for an SMB business at $120K. For enterprise level-companies, that figure rose to $2M.  Further, [A 2018 Study](https://www.a10networks.com/blog/this-is-how-much-time-and-money-ddos-attack-will-cost-you/) estimated the hourly cost of downtime for large businesses to be $300K - $540K, and [IBM's Cost of Data Breach Report 2020](https://www.ibm.com/security/digital-assets/cost-data-breach-report/#/) estimated the global average cost of a data breach at $3.86M, and the U.S. average at $8.64M.

Suffice it to say, DDoS attacks are both disruptive and costly to businesses, and increasingly commonplace. Therefore, it is  important for organizations to  have the technology needed to effectively 'weather the storm' at their disposal. In this project, we will assess the viability of using classification models to successfully identify traffic as malicious or benign, in an effort to maintain network/service availability.
<br></br>
## Goal:
The goal is to block as much of the malicious traffic from the DDoS attack as much as possible, while still correctly classifying all benign traffic. 

## Success Metrics:
Given benign traffic is our minority/positve class, success will be determined first by recall being 100%, and second by precision being as high as possible, ideally above 85%.

## Data Description:
The data used in this project has been used with permission from the Canadian Institute for Cybersecurity, located at the University of New Brunswick. The data includes network traffic logs across two days for multiple DDoS attack types, such as LDAP, SYN, PortMap, NetBIOS, MSSQL. Each dataset was simulated by the CIC, and is composed of malicious traffic labelled by DDoS attack type, and benign traffic meant to simulate legitimate traffic in the midst of a DDoS attack. The data is heavily imbalanced toward malicious traffic, as one would expect to see in a real-world situation.
<br></br>
## Tools:
- **Pandas**, **Numpy** for data ingestion, manipulation.
-**Seaborn** for visualization.
- **Scikit-Learn** for modelling, and evaluation.
<br></br>
## Models:
- K Nearest Neighbors
- Logistic Regression
- Binary Classification Models
<br></br>
## MVP Goal:
Produce a baseline module using all features present in the dataset and establish baseline metrics to inform further iterations.
