***Just write down what I want to don't forget***

## AWS Regions
### How to choose?
+ Data governance and legal requirements, Proximity to customers, Pricing, Available region
+ Geographically closest one choose near to me
+ There are some global services like Route53, IAM. But, EC2 is different according to regions.

<br><br>
## IAM
+ Identity and Access Management, Global service
+ Groups only contain users, not other groups
+ Users can belong to mutiple groups
+ Account user -> root user
### IAM Policies Structure
+ Sid : Statement id
+ Sid, Effect, Principle, Action, Resource, Condition
+ can create policy
### IAM MFA (for root account)
+ Multi factor authentication
+ Password you know + security device you own
+ If a password is stolen or hacked, the account is not compromised
+ Vitual MFA device ex) Auty, Google authenticator, U2F security key, other hardware MFA key
### IAM Security Tools
+ Account-level
+ User-level

<br><br>
## AWS CLI
### To access AWS
+ Management Console
+ CLI
  + https://docs.aws.amazon.com/ko_kr/cli/latest/userguide/getting-started-install.html
+ SDK (Software development kit)
+ AWS CloudShell
> Users manage their own access keys, Don't share them, Use MFA

<br><br>
## EC2
+ 

