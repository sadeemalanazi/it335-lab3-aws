In this lab, I configured core AWS security controls across IAM, S3, EC2, and monitoring to understand how proper cloud configuration can prevent real-world breaches such as the Capital One breach.

First, I worked with Identity and Access Management (IAM). I enabled multi-factor authentication (MFA) for the root account and created a restricted IAM user within a group that had read-only permissions. This demonstrates the principle of least privilege, where users are only given the minimum access required. In the Capital One breach, overly permissive IAM roles allowed attackers to access sensitive data. By restricting permissions, the impact of compromised credentials is significantly reduced.

Second, I created an S3 bucket and ensured that “Block all public access” was enabled. This configuration prevents unauthorized users from accessing stored data. In the Capital One incident, sensitive data was exposed due to misconfigured access controls. By enforcing private storage, the risk of accidental data exposure is minimized.

Third, I launched an EC2 instance and configured its security group to allow SSH access only from my specific IP address instead of allowing access from anywhere. This reduces the attack surface by limiting who can attempt to connect to the instance. In the Capital One breach, attackers exploited a Server-Side Request Forgery (SSRF) vulnerability to access the Instance Metadata Service (IMDS) and retrieve credentials. Restricting network access through security groups and using IMDSv2 helps interrupt this attack path.

Finally, I explored monitoring tools such as AWS CloudTrail and the Billing dashboard. CloudTrail logs all API activity, allowing administrators to detect unusual behavior. Billing dashboards can help identify unexpected usage that may indicate a compromise. Continuous monitoring reduces the attacker’s window of opportunity.

Overall, this lab showed that cloud security depends on correct configuration and awareness. Even small misconfigurations can lead to serious vulnerabilities, as seen in the Capital One breach.
