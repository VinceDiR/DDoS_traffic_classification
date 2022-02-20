# Identifying DDoS Attacks using Classification #
### By: Nate DiRenzo

## Statement of Need:

Distributed Denial of Service (DDoS) attacks are a common form of malicious activity intended to disrupt the operations of an organization. To accomplish this, DDoS attacks flood a victim network, service, or infrastructure with orchestrated junk traffic. This junk traffic swamps its target, severely limiting availability and oftentimes bringing it offline entirely.

DDoS attacks are effective and difficult to detect because they make use of multiple compromised computer systems as sources of malicious traffic, hence the 'Distributed' part in Distributed Denial of Service. These 'bots' (or 'zombies') are devices infected with malware that allows an attacker to control them remotely. The bots are orchestrated into what is called a 'botnet', and the attacker can orchestrate the attack by sending instructions to the botnet. Compromised devices could be any internet connected device, like as computers, but also more mundane IoT items like [smart regrigerators](https://www.gruntworx.com/smart-tv-secure/) or [thermostats](https://mashable.com/article/casino-smart-thermometer-hacked).

DDoS attacks are omnipresent in our internet-driven world. [The Digital Attack Map](https://www.digitalattackmap.com/#anim=1&color=0&country=ALL&list=0&time=18763&view=map) provides a live look at active DDoS attacks currently happening globally. DDoS attacks' ubiquity can likely be attributed to the relative ease with which they can be initiated. Further, some estimates place the cost of a month-long deployment of a mid-sized DDoS attack at [$311 on the Dark Web](https://www.missioncriticalmagazine.com/articles/93185-the-dark-web-ddos-attacks-sell-for-as-low-as-10-per-hour).

DDoS attacks are also directed at a wide variety of organizations. From Internet giants like [Google](https://www.pcmag.com/news/google-says-biggest-ddos-attack-on-record-hit-the-company-in-2017) and [Amazon](https://www.theverge.com/2020/6/18/21295337/amazon-aws-biggest-ddos-attack-ever-2-3-tbps-shield-github-netscout-arbor), to [financial institutions](https://www.wsj.com/articles/hackers-targeted-financial-sector-in-mass-extortion-campaign-11612909155), [gaming companies](https://www.invenglobal.com/articles/15807/ddos-attack-cripples-battlenet), [federal agencies](https://www.vox.com/recode/2020/3/16/21181825/health-human-services-coronavirus-website-ddos-cyber-attack), [journalistic publications](https://www.inverse.com/article/33520-new-york-times-reddit-ddos-attack), and [not for profits](https://www.computerworld.com/article/2495967/update--spamhaus-hit-by-biggest-ever-ddos-attacks.html). [GitHub](https://www.wired.com/story/github-ddos-memcached/) itself has even been subject to DDoS attacks.

It's difficult to quantify the business impact of DDoS attacks. Successful attacks can result in outright downtime, productivity constraints, data breaches, reputational damage, and loss of SEO ranking. Ransom and extortion-based DDoS attacks have also become more prevalent in reent years, meaning businesses are often forced to pay attackers large sums to stop an in-progress attack, in addition to incurring the traditional costs associated with DDoS attacks. 

A [2017 Kaspersky Survey](https://usa.kaspersky.com/about/press-releases/2018_ddos-breach-costs-rise-to-over-2m-for-enterprises-finds-kaspersky-lab-report) estimated the average cost of enduring a DDoS attack for an SMB business at $120K. For enterprise level-companies, that figure rose to $2M.  Further, [A 2018 Study](https://www.a10networks.com/blog/this-is-how-much-time-and-money-ddos-attack-will-cost-you/) estimated the hourly cost of downtime for large businesses to be $300K - $540K, and [IBM's Cost of Data Breach Report 2020](https://www.ibm.com/security/digital-assets/cost-data-breach-report/#/) estimated the global average cost of a data breach at $3.86M, and the U.S. average at $8.64M.

Suffice it to say, DDoS attacks are both disruptive and costly to businesses, and increasingly commonplace. Therefore, it is  important for organizations to  have the tools needed to 'weather the storm' at their disposal. In this project, we will assess the viability of using classification models to successfully identify traffic as malicious or benign, in an effort to maintain network/service availability.
<br></br>
## Goal:
The goal of this project is to identify all instances of benign traffic in a dataset heavily imbalanced toward malicious traffic, much like we would see in a real world scenario. More specifically, the goal is to correctly identify benign traffic 100% of the time, while minimizing the amount of malicious traffic misidentified as benign. In practical terms, this accomplishes the goal of ensuring services remaine accessible to legitimate traffic, while mitigated the effects of the DDoS attacks to as much an extent as possible.

## Success Metrics:
Given benign traffic is our minority/positve class, success will be determined first by recall being 100%, and second by precision being as high as possible, ideally above 85%.

## Data Description:
The data used in this project has been used with permission from the Canadian Institute for Cybersecurity, located at the University of New Brunswick. The data includes network traffic logs across two days for multiple DDoS attack types, such as LDAP, SYN, PortMap, NetBIOS, MSSQL. Each dataset was simulated by the CIC, and is composed of malicious traffic labelled by DDoS attack type, and benign traffic meant to simulate legitimate traffic in the midst of a DDoS attack. The data is heavily imbalanced toward malicious traffic, as one would expect to see in a real-world situation. In this project, I have focused exclusively on the DrDoS_LDAP dataset.

<br></br>
## Tools:
- **Pandas**, **Numpy** for data ingestion, manipulation.
-**Seaborn** for visualization.
- **Scikit-Learn** and **XGBoost** for modelling, and evaluation.
<br></br>
## Models:
- Logistic Regression
- Random Forest
- Gradient Boosting
<br></br>
## MVP Goal:
Produce a baseline logistic regression model using all features present in the dataset and establish first-pass metrics to inform further iterations.
