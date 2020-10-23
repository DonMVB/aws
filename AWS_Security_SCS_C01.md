\- [Basics - Terms and Foundations](#basics---terms-and-foundations)
  - [Security In AWS](#security-in-aws)
- [IAM (Recap from SAA C02 to Security) (Added 9/24/2020)](#iam-recap-from-saa-c02-to-security-added-9242020)
  - [IAM UI Review Notes](#iam-ui-review-notes)
  - [Root User leaves - Actions? (added 10/1/2020)](#root-user-leaves---actions-added-1012020)
  - [IAM Policy Review (Updated 10/1/2020)](#iam-policy-review-updated-1012020)
  - [IAM Credential Report (Added 10/1/2020)](#iam-credential-report-added-1012020)
  - [Polcy Doc Notes](#polcy-doc-notes)
- [S3 Bucket Policies (Added 9/29/2020)](#s3-bucket-policies-added-9292020)
  - [Lab (Added 9/29/2020)](#lab-added-9292020)
  - [S3 Access Control Lists (Added 9/29/2020)](#s3-access-control-lists-added-9292020)
  - [S3 ACL Lab](#s3-acl-lab)
  - [IAM and S3 Policy Conflict Resolution (Therapy?) (Added 9/29/2020)](#iam-and-s3-policy-conflict-resolution-therapy-added-9292020)
  - [Encryption on S3 (Added 9/29/2020)](#encryption-on-s3-added-9292020)
  - [Cross Region Replication and Encryption (Added 9/29/2020)](#cross-region-replication-and-encryption-added-9292020)
  - [Securing S3 using CloudFront (Added 9/29/2020)](#securing-s3-using-cloudfront-added-9292020)
  - [Secure S3 using Pre Signed URL's (9/29/2020)](#secure-s3-using-pre-signed-urls-9292020)
- [Cloud Front (Added 9/29/2020)](#cloud-front-added-9292020)
  - [Using your own Certificate](#using-your-own-certificate)
- [Security Token Service (STS) (Added 9/29/2020)](#security-token-service-sts-added-9292020)
- [Cognito, a Web Identity Federation (Added 9/29/2020)](#cognito-a-web-identity-federation-added-9292020)
  - [Cognito User Pools](#cognito-user-pools)
  - [Lab: Cognito User Pool (Added 9/29/2020)](#lab-cognito-user-pool-added-9292020)
- [Logging in AWS General Notes (Added 10/1/2020)](#logging-in-aws-general-notes-added-1012020)
- [Cloud Trail Logging (Added 9/30/2020)](#cloud-trail-logging-added-9302020)
  - [Lab - Setup Cloud Trail](#lab---setup-cloud-trail)
  - [Cloud Trail Integrity: Securing Log Files (Added 9/30/2020)](#cloud-trail-integrity-securing-log-files-added-9302020)
  - [Lab - Lifecycle](#lab---lifecycle)
- [CloudWatch: (Added 9/30/2020)](#cloudwatch-added-9302020)
- [Cloud Flare](#cloud-flare)
- [AWS Confiog (added 9/30/2020)](#aws-confiog-added-9302020)
  - [AWS Config Lab (added 9/30/2020)](#aws-config-lab-added-9302020)
- [Alert Conditions - Root User Login (Added 9/30/2020)](#alert-conditions---root-user-login-added-9302020)
- [Cloud HSM (Added 9/30/2020)](#cloud-hsm-added-9302020)
- [Inspector vs. Trusted Advisor (Added 10/1/2020)](#inspector-vs-trusted-advisor-added-1012020)
- [Glaciuer Vault (Added 10/1/2020)](#glaciuer-vault-added-1012020)
- [AWS Organizations and Service Control Policies (added 10/1/2020)](#aws-organizations-and-service-control-policies-added-1012020)
- [Amazon Key Management Service (KMS) (Added 10/1/2020)](#amazon-key-management-service-kms-added-1012020)
  - [Lab for KMS](#lab-for-kms)
  - [Setup customer managed key](#setup-customer-managed-key)
  - [KMS Key Rotation Options (10/15/2020)](#kms-key-rotation-options-10152020)
  - [Customer Managed Key Pairs on Mac (Added 10/14/2020)](#customer-managed-key-pairs-on-mac-added-10142020)
  - [KMS and EBS (Added 10/16/2020)](#kms-and-ebs-added-10162020)
  - [KMS Grants](#kms-grants)
  - [Key Policy Conditions by Service](#key-policy-conditions-by-service)
  - [Cross Account Access for Customer Master Keys](#cross-account-access-for-customer-master-keys)
  - [EC2 and Key Pairs (Added 10/16/2020)](#ec2-and-key-pairs-added-10162020)
- [MarketPlace Security Products](#marketplace-security-products)
- [AWS WAF and AWS Shield (Added 10/16/2020)](#aws-waf-and-aws-shield-added-10162020)
- [EC2 Dedicated Instancs vs Dedicated Hosts  (Added 10/16/2020)](#ec2-dedicated-instancs-vs-dedicated-hosts-added-10162020)
- [Hypervisor Security and resource isolation (Added 10/16/2020)](#hypervisor-security-and-resource-isolation-added-10162020)
- [Microservices (Added 10/17/2020)](#microservices-added-10172020)
- [Containers (Added 10/17/2020)](#containers-added-10172020)
  - [Best Practices for Containers (Added 10/17/2020)](#best-practices-for-containers-added-10172020)
  - [ECS Sample Application in the Console](#ecs-sample-application-in-the-console)
- [Creating a Custom VPC (Added 10/17/2020)](#creating-a-custom-vpc-added-10172020)
- [NAT Instances and Gateways (Added 10/17/2020)](#nat-instances-and-gateways-added-10172020)
- [NACL vs. Sec Groups (added 10/17/2020)](#nacl-vs-sec-groups-added-10172020)
- [Load Balancers and Custom VPC's (Added 10/19/2020)](#load-balancers-and-custom-vpcs-added-10192020)
- [Elastic Load Balancers (ALB's) and TLS / SSL Termination (Added 10/19/2020)](#elastic-load-balancers-albs-and-tls--ssl-termination-added-10192020)
- [VPC Flow Logs (Added 10/19/2020)](#vpc-flow-logs-added-10192020)
- [NAT vs. Bastion Servers (Jump Boxes) (Added 10/19/2020)](#nat-vs-bastion-servers-jump-boxes-added-10192020)
- [Systems Manager Session Manager (Added 10/19/2020)](#systems-manager-session-manager-added-10192020)
- [Systems Manager Parameter Store (Added 10/23/2020)](#systems-manager-parameter-store-added-10232020)
- [System Manager Run Command (Added 10/23/2020)](#system-manager-run-command-added-10232020)
- [VPC End Points (Added 10/19/2020)](#vpc-end-points-added-10192020)
  - [VPC Clean Ups (Added 10/202020)](#vpc-clean-ups-added-10202020)
- [AWS Cloud HSM (Added 10/19/2020)](#aws-cloud-hsm-added-10192020)
  - [Cloud HSM User Types (Added 10/19/2020)](#cloud-hsm-user-types-added-10192020)
  - [Cloud HSM Comamnds of Note (Added 10/19/2020)](#cloud-hsm-comamnds-of-note-added-10192020)
  - [Clean up (Lab Tear Down) (Added 10/20/2020)](#clean-up-lab-tear-down-added-10202020)
- [Amazon DNS and Custom VPC's (Added 10/20/2020)](#amazon-dns-and-custom-vpcs-added-10202020)
- [Transit Gateway (Added 10/20/2020)](#transit-gateway-added-10202020)
  - [DDOS and Real World (Added 10/20/2020)](#ddos-and-real-world-added-10202020)
- [Incident Response Scenarios (Added 10/20/2020)](#incident-response-scenarios-added-10202020)
  - [EC2 Hacked - What to do? (Added 10/20/2020)](#ec2-hacked---what-to-do-added-10202020)
  - [Leaked Credentials in Source Code Site (Added 10/20/2020)](#leaked-credentials-in-source-code-site-added-10202020)
  - [Reading Cloud Trail Logs (Added 10/20/2020)](#reading-cloud-trail-logs-added-10202020)
- [Penetration Testing in AWS Added 10/20/2020)](#penetration-testing-in-aws-added-10202020)
- [Certificate Manager (Added 10/20/2020)](#certificate-manager-added-10202020)
- [Securing Load Balancers with PFS (Added 10/20/2020)](#securing-load-balancers-with-pfs-added-10202020)
- [API Gateway (Added 10/23/2020)](#api-gateway-added-10232020)
- [Compliance Frameworks (Added 10/23/2020)](#compliance-frameworks-added-10232020)
- [AWS Athena (Added 10/23/2020)](#aws-athena-added-10232020)
- [AWS Macie (Added 10/23/2020)](#aws-macie-added-10232020)
- [GuardDuty (Added 10/23/2020)](#guardduty-added-10232020)

This study guide paralles the A Cloud Guru Q3 2020 AWS Security course.
# Basics - Terms and Foundations
These are core InfoSec topics you must know
- CIA - Confidentiality, Integrity, Availability (IAM, MFA / Certificatss, IAM, Bucket Policies / HA, Multi AZ, )
- AAA - Authentication, Authorization, Accounting (IAM, Policies, Cloud Trail)
- Non Repudiation - Unable to deny in public setting (IAM + MFA + Cloud Trail)
- Shared Responsibility Model - https://aws.amazon.com/compliance/shared-responsibility-model/?ref=wellarchitected Note that the model changes per service type
- "Of" the cloud and "In" the cloud - you are responsible for how you use, implement, instrument, and permit access to the various in AWS
- Regulatory: Numerous independent bodies have audited / reviewed AWS.
- Containers: Up to the OS and in many cases the app itself (RDS is a good example)
- Abstracted Services: You are responsible for the data in these (S3, Clacier, Dynamo DB)
- Controls: Visibility, Auditability, Controlability, Agility, Automation, Scale

## Security In AWS
- Bill Murry - AWS security should be as familiar as what you do in your data center -> Visibility, Auditability, Controlability, and Agility. Add a few more though: Automation and Scale.
- Asset visibility Tools-AWS Config, Cloud Trail
- Scale is on your side: all customers get the same set of services available to them!  No differentiaon based on customer size, type.

### AWS Services for Security
- AWS Config (Visibility)
- Discover entire asset stack in AWS. Under Management Tools. Can search for some or all resources and save to a S3 bucket.   There are numerous rules that can be used to check out individual AWS capabilities. 
- Can also find deleted resources. Takes a bit of time to load.
- AWS Clud Trail (Auditability)
- AWS KMS and Cloud HSM (Data control)
- KMSL multi tenant w/ strict controls. 
- Cloud HSM w/ dedicated HW (more expensive) Cloud HSM is FIPS 140-2 compliant. 
- Ability AWS Cloud Formation and Elastic BeanStalk
- Repeatable AWS OpsWorks and AWS Code Deploy
- Others: IAM, CloudWatch, Trusted Advisor (limited in free tier)

# IAM (Recap from SAA C02 to Security) (Added 9/24/2020)
- Need to know how to manage IAM and how IAM Policies relate to other services. Can't be managed by a "PowerUser", only an "Admin" user. 
- Controlling access to "root": Delete (preserve) Keys, enable MFA, create secondary admin accounts.
- IAM: Central control of users (people), groups (of users), roles (often assigned to EC2 and other services). policies (applied to groups who then inherit). Password policies. Share access. Granular perms. Identity Federation. Setup MFA. Temp access grants. 
- Supports many regulatory, rqmts. 
- Policy: A JSON DOC with a specific grant for specific rights to a AWS service. Created via the Visual Editor, can review the JSON doc as well. Always use `Principle of least privilege`.
- Example: Create a user, give them "S3 Full" only, and they should have access to see just S3 content and then denied to other services (splash screen/dash w/ no data thought). Try to create an S3 policy for "read/write", not "bucket create".
- IAM policy conflict resolution (IAM therapy?)
- Tips: Global, 3 policy types (AWS managed, customer managed, inline), 

## IAM UI Review Notes
- Security Status quick check - Delete Root keys,
- My Sec Credentials UI
- User Sec Creds: Password, add MFA (can deactivate and then re-activate for a refresh), 
- Virtual MFA: You should make a screen shot of the QR code!

## Root User leaves - Actions? (added 10/1/2020)
- These actions need to be performed by the new admin: Deactivate/reactive MFA on the root account, review IAM users and remove any accounts the former admin owned, changed the root password, delete any root owned access / secret keys.

## IAM Policy Review (Updated 10/1/2020)
- Specify what you amy do with an AWS resource. Applied to user, group, role. Or what can a priciple do in AWS. To apply a policy to an EC2 instance, you need to create the policy, apply it to a role, and attach the role to the EC2 instance.  IAM policies can't be attached to S3 buckets. 
- Three types: AWS managed, customer, inline.  Policy names are links to JSON objects. 
- AWS Managed: Shared across AWS, who defined them. Can change occassionally (usul. minor). Read Only, Admin, etc. Indicated with yellow box icon.
- Admin user: everything but billing.
- PowerUser: everything but IAM and changes in there.
- Customer Managed: Standalone, in an AWS account, then can be applied. Can cut/paste across accounts, can't "send over". 
- Inline: Strict 1:1 relationship between policy and its entity. Very directed. 
- Path: Console: Security and Compliance -> IAM. User | Group - attach policy during creation. 

## IAM Credential Report (Added 10/1/2020)
- A CSV with user, ARN, creation time, PW enabled, pw-last-used, MFA Active.
- Easy to generate: Console | Services | IAM | Credential report (left side).  Then "Download". 
- Just as easy to generate via comd line
  - `aws iam generate-credential-report`
  - `aws iam get-credential-report`
- Requires "GenerateCredentialReport" and "GetCredentialReport" permissions. 

## Polcy Doc Notes
- Version
- Statement
- Effect
- Action
- Resource

# S3 Bucket Policies (Added 9/29/2020)
- Specify what can / cannot be done on a bucket by user. Ann can PUT, Joe can PUT & DELETE.
- Can grant cross account access for other acconts to read/write bucket.
- Can solve for size limits. IAM policies = 2 KB for users, 5KB for groups, S3 bucket policies = 20 KB.
- Practically, it is often easiter to manage Access Control at the bucket level than to work w/ IAM policies and apply them.
  - Easier to grant a "Allow 3, deny all else" policy.
  - Set at the Bucket Level.
- All S3 access is blocked to 'public' by default (AWS answer to bad user mgmt.)
- An "Explicit Deny" will alwas trump an "Allow". You can "Deny All", then "Allow One", and One will still be denied.
- To grant EC2 access to S3, you can create an IAM role with read access to the bucket and associate the role w/ the EC2 instance.

## Lab (Added 9/29/2020)
- Create two buckets and two IAM users. By S3 policy, deny a user from read/write but allow them via IAM policy.
- Console | S3, Create buckets. S3 | Permissions | Access Control List.   S3 | Permissions | Bucket Policy. Copy ARN. 
- IAM | User - grab users ARN. 
- Use the Policy Generator. Principle = ARN o/t User. Actions - allow user to "delete".  Get the S3 ARN. Add Stmt if you want more. Review the JSON. 
- Can paste in the JSON - will get an arror. Need to give a direction, which would be /* for the entire bucket.
- Create a second S3 bucket. Test user A and B "PUT" on the second bucket. Then test User A & B Put in the First bucket. An error should appear in ... ?
- Create a new S3 bucket policy on bucket A. That should be set to Deny All, then "allow" User A. Objective is to generate conflicting policies and observe actions. Within console, should get errors on S3 page - not even region.
- Using the direct link (URL) for a item marked as "Public" bucket works because you are not using any authentication mechanism. Different than an "open" in the console S3 panel because console is 'authenticated'. 
- Working through the Policy Editor, use something like Create Policy. Can "Edit" a policy, change the Actions, adjust Access Level Groups. Then edit the JSON directly. Note that if you do this - the "name" of the policy should reflect the end state change. JSON is case sensitive. 

## S3 Access Control Lists (Added 9/29/2020)
- Predates IAM policies. On the per file / per object basis. 
- Use Cases: fine grained permissions.  
- Can set very specific permissions.

## S3 ACL Lab
- Add a file to a bucket with no bucket polices (applying only IAM policies).
- On Permissions | Access Control List, Chose Add to grant for "Access to other AWS account".
- On an object, adjust the individual object Permissions. 
- Can't edit permissions for IAM users. Must use CLI or the SDK API which require account number and the Owner Canonical User ID. Acct #'s are avail under "My Sec Creds" and the Canonical User ID is under "Account Identifiers" for root. Use `AWS S3 API list-buckets` to get the individual user Can-ID. 
- These numbers can then be used in the object ACL definition. 

## IAM and S3 Policy Conflict Resolution (Therapy?) (Added 9/29/2020)
- When IAM conflicts w/ S3 Policy and S3 ACL, decision is based on union of all three.
- Least Priv: Decision defaults to DENY. 
- Explicit Deny trumps ALLOW (override property)
- If one or more methods specify an allow and there is no deny, access is alloed.
- Pathway (memorize this, and practice it on some JSON)
  - Decision starts at DENY
  - Eval applicable policies
  - Is there explicit Deny? Thats it, deny.
  - Is there an explicit Allow? Allow access.
  - If neither an allow or deny, then deny.

## Encryption on S3 (Added 9/29/2020)
- Want to ensure we use HTTPS, not HTTP on a bucket you want to make 'Public'. Done via a bucket policy. Setup an allow, then an explict deny, add a Condition of type Bool named "aws:SecureTransport": false. Or setup an "allow" and then a "deny" with a specific condition.
- In the Console, S3, Permissions | Bucket Policy, copy the JSON into the bucket policy (don't forget to add /* on both resource entries.)
- To test this, can get the URL and use http://, not https://.
  
## Cross Region Replication and Encryption (Added 9/29/2020)
- CRR: need to refresh on 'Associate' info (all assumed.)
- By default, CRR is done via SSL/TLS. Data can only be replicated from one source bucket to one destination bucket. Objects can't be replicated again. 
- Rqmts: Src/dest must have versionioning enabled. Must be in different regions. S3 must have replication permissions - a customer managed policy is setup for you by the console. 
- When the bucket owner owns the object(s), the bucket owner can replicate. If not, then obj owners must grant READ and READ_ACP permissions to the ACL.
- CRR does work across accounts. The owner of the DEST bucket must grant permissions to the owner of the SOURCE bucket to replicate with a bucket policy (Dest accepts incoming). IAM role must have permissions in the DEST bucket, which requires CRR and a role. Can also change the ownership to the dest bucket owner during replication. Can be applied to Cloud Trail audit logs for enhanced security - replicate the source CT Logs to a dest, so they can't be touched as the owner changes to dest on replication. (Powerful IR prep action.)
- What is replicated? New items as they are added only. Will replicate unencrypted, and follow rules for encrypted. Metadata. ACL Updates. Tags. Objects w/ read + read ACL permissions. 
- Deletes: the delete marker is replicated, but underlying versions are not there.
- Not replicated: Objects encrypted w/ Server Side Encryption (customer supplied keys). Deletes to a particular version. 
- Encryption rules: SSE-S3, SSE-KMS. Need to explicitly enable KMS key encryption. 

## Securing S3 using CloudFront (Added 9/29/2020)
- You can force a user to use a CloudFront URL for an underlying S3 bucket. Remember, there is a cost to CloudFront.
- Network | CloudFront: When you create a distribution, it can take up to 15 minutes for the dist to be global.
- To use a custom TLS Certificate, you need to import a certificate via Amazon Certificate Manager (ACM). Not the same as a load balancer certificate (no borrowing).  Note that certificates are stored in ACM in us-east-1.
- For S3 bucket based static websites where you want them hosted only through CloudFront, perform these actions.
  - Configure S3 bucket so only the Origin access identity has 'read'.
  - Select 'Restrict bucket access' in the origin settings of the CloueFront Districution.
  - Create an origin access policy for S3 origin.

Lab: 
- Need the Origin domain name and then defaults. Pause - check back in 15 min.
- Add an object to the S3 bucket you want to be replicated via CloudFront. Ex. s3.eu-west-2.amazonaws.com/yourbucketnamehere.
- Inside Cloud Front, check the box and update the Origin to edit. Then 'restrict bucket access'. You need the Origin Access Identity, which is a specific CloudFront user (new or reuse existing).  Also check "Grant Read permissions on bucket". Main steps - Edit Origin, new/reuse identity, grant permissions. Note that this update can take a while to take effect (4 to 48 hrs).

## Secure S3 using Pre Signed URL's (9/29/2020)
- Need an IAM role for EC2, grant AmazonS3FullAccess, and assign to applicable EC2 instances. Launch an Instance and add the role. (Don't forget about key pairs.) S3 buckets in this case start as 'private'. 
- Command: `aws s3 presign s3://path/file`. By default, this command will presign for 60 seconds. To chage, use `--expires-in SECONDS`. You will get a long presigned URL, with the file, an ID, an expiratin, and a URL encoded token on the URL line. Can copy/paste, and get access. 

# Cloud Front (Added 9/29/2020)

## Using your own Certificate
- To preserve domain identity and not have users accessing Cloud Front w/ its own certificate and domain (*.cloudfront.net), need to update the certificate. 
- In the console, under Distribution Settings, can select "Custom SSL Cert." Two choices where to store - AWS Cert Mgr (ACM) (in US-East-1 Region) or can store in Identity Mgr using the CLI.
  
# Security Token Service (STS) (Added 9/29/2020)
- Grantes limited and temporary access to AWS resources. 
- Users can come from Federation, Mobile app (Facebook, Google, ... OpenID), Cross Account access.
- Specific to Active Directory, users don't need an IAM account but must visit the ADFS sign in page to gain access.
- Federation: Combining or joining users from Domain A w/ Domain B.  Handled by an Identity Broker. Each side has an Identity Store. Identity = user. 
  - Active Directory 
  - SAML Assertion
- Example: An IPSEC VPN joins campus to AWS resources. A web app in AWS can auth against on-prem AD. Any app can ask an "Identity Broker" against an LDAP to validate identity. The identity Broker calls GetFederationToken using IAM creds w/ the IAM policy + duration, and grant policy. STS validates these. STS returns an access key, secret access key, token, and token lifetime duration.  Applications can further pass down the STS token on behalf of the user. 

# Cognito, a Web Identity Federation (Added 9/29/2020)
- WIF allows us to give temp AWS creds after someone has authenticated with well known web-ID providers. Users get an auth code (JWT). Third parties must support / provide Amazon Cognito.  Can also (apparently) permit anonymous guest access. (ACG Sec Test Q.)
- Amazon Cognito: Sign up / Sign In, server "guests", is an ID Broker, Synch up data on mobile, recommended for mobile apps and AWS services.

## Cognito User Pools 
- User Pools - Directories used to manage sign in / sign up.  Successful auth gen's up JWTs (the authentication piece.)
- Identity Pools enable us to create unique IDs for users. More to do with assigning roles to users who have already authenticated (the authorization piece.)

## Lab: Cognito User Pool (Added 9/29/2020)
- Console | Security Identity | Cognito.
- Manage User Pools, Create w/ a usable name. Most of the defaults are OK. 
- Add an App Client - again, need a usable name.  This is used to call API's on our behalf. Cofigure the app client, which will be Cognito user pools. The Callback user URL will be where users are redirected back to once successfully auth'd. There is also a sign up URL. ON OATH - Check both Auth Grant and Implicit Grant (provides the JWT). Normally will also check all OATH scopes.  
- Create a domain name as a prefix for Cognito, added to `.auth.region.amazoncognito.com`.
- The sign in and sign up pages can be customized (UI makes this fairly easy).
- Under App Integration, get the name. Need to add some params - /login?response_type=token&client_id= and you need the App Client ID - and then some more params b/c you are generating a one-off URL. Will get a sign up / sign in page. (actually kinda nice!)
- The site also can send (and you should send) an end user verification code. 

# Logging in AWS General Notes (Added 10/1/2020)
- Major serivces - there are four. 
  - AWS CloudTrail as it happens. Enable in each region where you have an account / resources. 
  - VPC flow logs as they happen.
  - AWS Config provides a point in time view of configuration and change history.
  - AWS Cloud Watch logs performance of assets.
- White Paper: Security at Scale: Logging in AWS. Focuses on ISO 27001:2005, PCI DSS, and FedRAMP.
- Must control access, use bucket policies, S3 bucket policies, MFA, and replicate log data to protect it.
- Always log changes to system conponents.
- Cloud Trail validation and encryption as well. 

# Cloud Trail Logging (Added 9/30/2020)
- A web service that records API calls for your account. Delivers logs to S3 bucket. Provides after incident investigation. Not really 'real time' delivery. Every 5 minute delivery schedule, up to 15 minute delay. Most, but not all, AWS services generate a log record.  Logs go to S3, which you must manage. 
- We interface with the cloud through the `control plane` (critical concept.)
- For example, `aws s3 mb s3://somesortofbuckethame` will be recorded in CloutTrail logs. Both the console and CLI go through. 
- RDP and SSH are not logged via Cloud Trail - native OS logging must accomodate.
- Supported: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html
- Unsupported: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-unsupported-aws-services.html
- Cloud Trail limits: https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html :: 5 Trails per region, 10 trans/second
- Typical log record - Metadata, Caller Identity, time, Src IP, request params, service response
- Sent to S3 bucked, customer manages file retention. Can aggregate across region, account. Idea is to centralize logs. Bucket isn't visible by default for initial setup. 
- Provisioning: Management Tools | Cloud Trail shows recent events. On for 7d by default at account start - then user needs to enable. Create a Cloud Trail - all regions, want 'all event' types, can enable S3 down to the object level ($), and storage location where you create the S3 bucket. Can define a logfile prefix. Also, enable SNS notification (huge amount of info...)
- Digest files require Log Trail validation to be enabled. They are SHA 256 bit hashed w/ a private key, can validate using the command line.

## Lab - Setup Cloud Trail
- Once you set up CloudTrail, do something like run a Cloud Formation setup. Wait a bit (20 min).
- Go back into CloudTrail, check events. Go to S3, look at the cloud Trail bucket. Cloud trail createsa "CloudTrail" directory and drops off logs and a "CloudTrail-Digest" directoryu with digest files by region - so there will be about 20 sub directories. In those directories are the Cloud Trail specific logs. Digest files take a little longer. 

## Cloud Trail Integrity: Securing Log Files (Added 9/30/2020)
- Why Protect? CT logs contain detauled config info plus AWS user identity info. Can use encryption.
- How do we restrict to just Sec Ops? Put the SecOps in an IAM role, grant them access in S3 bucket (not an admin group). We want least priv though. Create a policy with "AWSCloudTrailReadOnlyAccess" to users who need 'read', like auditors. Sec Admins get the 'full' policy.
- Modified? Configure SNS notifications. Send notification to responsible party (Sec Ops). 
- Prevent Delete? Restrict delete access, enable S3 MFA Delete. 
- Retention? Kept indefinitely, use S3 obj lifecycle mgmt to remove or move to Glacier.

## Lab - Lifecycle
In S3, click on the CloudTrail bucket. Mgmt tab. Lifecycle rule. Name *well*.  Configure expiration, after X days after creation, then save. 
In S3, Properties.  Encryption on the bucket isn't enabled.  Drill into an individual log - see that there is AES 256 bit encryption on the file.

# CloudWatch: (Added 9/30/2020)
- A monitoring service for AWS resources - plus a bit more. Resource utilization, op performance, analsysis, applications. Near real time. Hooks into 'event triggers'.
- Components: CloudWatch, Logs, Events. 
- CloudWatch: 
  - RealTime if you enable 'detailed' for every one minute, 5 min by default. 
  - Metrics 
  - Alarms
  - Notifications
  - Custom Metrics - anything you can program, can pass to CW API.
- Console: Mgmt Tools | CloudWatch for the landing page. 
- You will end up creating a dashboard w/ a variety of widgets for metric views. Charts, numbers, line graphs, ...
- Creating Alarms: Need to add 'create alarm', such as a billing alarm. Select the metric, CPU, per instance, get the instance ID, name it well, then the comparison (metric) value, and the period of time. Select the state, and then an email notification. Whats important - you can create metrics, need to pass data into CloudWatch.
- Cloud Watch Logs
  - Pushed from various AWS services (including Cloud Trail)
  - Your apps can script
  - Need to setup a 'log group', which can then be searched
  - Setup: Create a log group. Need to also deploy an agent to an OS.
- Cloud Watch Events
  - The Control Plane is monitored via Cloud Trail as API's are run - which can also go to Cloud Watch. We can configure Cloud Watch as an event source. Rules can be setup in CW for notification, like provisioning an EC2. We configure an Event Target for these. A Lambda event can then take further action.
  - Logged types include AWS resource state changes, Cloud Trail, code driven custom events, scheduled events. Rules monitor and route to a target (kinesis, SNS topics, SQS).
  - Create a rule: need the event pattern by service.  Rules can have multiple event sources. Set a target - of which there are several. 
- How do we control? IAM policies and actions. Can't decouple from source though.
- Prevent unauth users? AWS access, IAM policies, API's use signed requests. 
- Read the FAQ's ...

# Cloud Flare


# AWS Confiog (added 9/30/2020)
- Asess, audit, eval configuration of AWS resources. Allows you to automate evaluation against desired config. Like a security camera, with a historical timeline, to find when a configuration changed. Can configure auto remediation (like PowerShell DSC). (really cool dashboard too!)
- Example: If someone makes an S3 bucket public, you can get a notice. 
- Enables compliance auditing, config checks, resource tracking. Requires an IAM Role with Read only permissions to the recorded resources, WRite to S3 logging bucket, and publish to SNS topic(s). 
- Best practice is to restrict access to AWS config. Only Admins need setup. Use cloud trail with config for a deeper view. Cloud trail alerts for changes to AWS Config is a must. 
- System has conformance packets as well.
- Works with two types of rules.
  - AWS Managed rules - you supply some config params to get started. About 80.
  - Customer Managed - Customer created, can talk to Lambda to change things for you. 
- Process: Someone changes a setting. AWS Config observes. If the change relates to a rule, the engine can notify or revert the change.
- Conformance Packs: A collection of rules and remediations. Authored in YAML. 
- Aggregator is a config resource type that collects from single / multple or single / multiple regions - across multiple accounts. Changes are actully made by AWS Systems Manager. 
- Enabled on a region by region basis.- 

## AWS Config Lab (added 9/30/2020)
- Note: Need to enable for each regions. Mgmt & Governance | Config | Get Started.
- Specify the resource types including global. Storage in a named S3 bucket (lower case bucket name). Can also create a SNS topic. Can use an existing role.
- Review the rules pane. Confirm the rules you want enabled. 
- If there is a notification, go and review the rule and affected resource.  Variety of 'actions' can be done. Auto or Manual. 
- Can view the resource timeline (which looks nice!)
- Aggregated views: 
- Review conformance packs.  Note that there are sample templates. 

# Alert Conditions - Root User Login (Added 9/30/2020)
- Accomplished with native tools: Cloud Trail, Cloud Watch, Custom Metrics, SNS.
- Cloud Trail needs to be setup. Send the CT logs to CloudWatch Logs in a new or existing log group. CT asssumes a role, and grants permissions (hit allow in the console).
- In Cloud Watch, edit the Cloud Trial log group. Create a metric filter. Something close to this: { $.useridentity =  "root" && $.useridentity.invokedby NOT EXISTS && $.eventtype != "AWSServiceEvent" }
- Assign Metric with a good name like "AlertOnRootLogin". From there, you need to create a alarm so that the filter can cause action. 
- Alarm name should be well defined. If the filter occurs > 0 times, 1 out of 1, create a notification and enter an email address. Note that end users need to confirm the subscription. 
  
  # Cloud HSM (Added 9/30/2020)
  - When launched, the setup fee was $5K. Today, charged at $1/hr. Solid skill to amass if you can. Requires private subnets. 
  - HSM: Hardware Security Module, dediczted to your account. Appliance. Generates, stores pub/priv keys, and performs cryptographic operations on request. 
  - Provides: Secure storage, Crypto ops. 
  - Compare w/ KMS. HSM is single tenant, clustered, we are under key control, braod support, FIPS 140-2 support.  HSM is more expensive than KMS.
  - HSM is secured: AWS can admin the appliance, not the key operations stored. They could destroy partitions - but likely wont.  Has tamper evident desctructive controls. Fi the crypto officer fails 5x, system will erase itself (which is ... one way ...)
  - Monitor - must use cloud trail!
  
- Setup: Inside a VPC, private subnet, an EC2 control instance w/ cloudhsm_mgmt_util and key_mgmt_util packages. 
- Lab includes VPC, pub/priv subnet, cluster, HSM identity, launch an EC2 instance w/ packages. activate the cluster.

# Inspector vs. Trusted Advisor (Added 10/1/2020)
- Inspector: automated security assessment with an output report. Must be installed on an instance.  There is an Amazon AMI w/ Inspector agent on it though.  Inspector is setup on a per region basis - so if yuo are in 3 regions, you have three configurations. 
- Assessment Target, install agent on EC2, create and run a template. There are two broad categories - Netwok and Host. Host does include the CIS bench markes! Takes up to an hour to run. You get detailed notes on a per OS basis - like items that need an update.
- Inspector provides outputs by four severities: High, Med, Low, Info.
- Does not abdicate your responsibilities under the "Shared Responsibility Model".
  
- Trusted Advisor is a differnt item. TA is focused on cost, performance, security, and fault tollerance. Has core checks. 
- TA has a 'basic' and a 'business/enterprise' level.

- Key difference: Inspector runs a network and host assessment, whereas Trusted Advisor addresses how you are using the environment as a whole. Each cover different areas.

# Glaciuer Vault (Added 10/1/2020)
- Recap: Very cheap option for data archives. As little is 0.004/GB/Mo. A Glacier Vault is a container that stores Glacier ARchives
- Vault Lock policy: Can configure a WORM archive, or a X-Yr retention. Thats done w/ a policy that prevents delete < 5 yrs old. In the JSON this is "Deny-based-on-archive-age" against the ARN of the Vault. 
- Two steps in a Vault Lock.
  - Initiate the lock by attaching a Vault Lock policy. 
  - You now have 24 hrs to validate. Cannot change this after 24 hrs elapsed. So - make sure this is what you want.
  
  # AWS Organizations and Service Control Policies (added 10/1/2020)
  - Account mgmt services to consolidate multiple indiv accounts. Central mgmt for consolidated billing, impost Org Unites and apply "Service Control Policies" to the accounts.
  - Root node, the master account, should have no resources: Just for billing and service control policies. Under root there are org units. A hierarchy. 
  - Service Control Polcies are applied to all below at org unit and below. These create "permissions boundaries" to restrict what users, groups, roles, in those accounts can do. Includes the root account in accounts within the AWS Org. 
  - SCP's can "deny" access, not "Allow" access.  For example, you could restrict access to S3 accross a number of AWS accounts by creating a deny SCP. 
  - Ex. Effect: Deny, { Action"cloudtrail:StopLogging", "Resource":"*" } will prevent someone from turning off logging (JSON isn't perfect ...)
  
  # Amazon Key Management Service (KMS) (Added 10/1/2020)
  - NOTE: KMS is huge for the exam: Must know inside / outside / all around.
  - Multi tennant Managed service that makes it easy to create/control encryption keys. To separate, Uses HSM's.  Integrated with many services.
  - Users can protect thier data by being issued keys.  KMS is region based!  Group: AdministratorAccessPermission. A backing key is a prior use key, kept to decrypt older data.
  - Customer Master Key (CMK)
    - AWS Customer Master Key and the Customer managed customer master key. 
    - Attributes - Alias, create date, description, key state, key material. 
    - Key material can be AWS or customer provided.
    - You can *never* export a KSM key from KMS. 
    - Each service has its own managed key. These are mapped on a per region basis. 
  - Imported Keys:
    - Customers can provide key material to build customer managed keys. Can import a symmetric 256 bit key and use ot. 
    - Imporiting your own key material - might do this to affirm entroyp (randomness); to delete without the 7-30d wait (imediate). Also to be resiliant to AWS failure by escrowing keys outside of AWS. 
    - Avail / Durability is different. No automatic rotation with customer managed keys. 
  - S3:
    - We can see encryption in use on KMS. Won't work with anonymous access.
    - From within the AWS console, auth'd users can open files b/c users have access to the key. 
    - Users can also download.
  - IAM: How can you make access more secure?
    - Can grant access to keys, like we can grant admin access to a given key. 
    - Can grant "key user" access. 
    - Changing a group (like full access to SystemAdministrator) assigns a subset of access. For KMS, there are common usage capabilities. 
  - Key delete 
    - Can't directly delete. Instead, can schedule a key for delete - minimum 7d wait. (protection period). Key is marked as "Pending Deletion".
    - Can create a cloud trail + alert + SNS notification to see these though. 
    - Once a key is pending deletion, you will get errors upon any file access attempt. 
    - Root User can cancel key deletion, which will leave the key as disabled. Must specifically enable. 
  - New EC2 instance
    - Can enable EBS volume encryption at the "Add Storage" step. You see the name in select dropdown, adn then the ID in the EC2 window. 
  - Encrypted Key Materials
    - On an EC2 Linux AMI< you can perform OpenSSL actions to setup key material.  Can be done on a Mac and on Windows, but troubleshooting can be a pain.
    - Bucket, then EC2 instance, a role to grant access to a bucket (S3FullAccess is easiest). 
    - EC2 - standard create process w/ a T2 micro. Add in the S3 role. (remember the keypairs)
    - KMS: we need a new Master Key. Symetric, and "external key material origin".  Give it a solid alias. Assign a key admin.
    - Wrapping Key: When creating your own key material, you need a "wrapping key" from KMS.
      - Wrapping algorithim - like SHA1 for SSL. Timebox - 24 hrs. Download wrapping key and the import token (need both). Where did they go? need to know!
      - Next you will upload the wrapped key material to your intermeidate movement bucket.
      - On a linux system, run 'openssl version' to make sure its there. List out your S3 buckets with "aws s3 ls". Then "aws s3 cp://bucket/key-material --recursive' to the EC2. 
      - Run OpenSSL the commands to create the plain text key material. 
      - The public key is the AWS wrapping key to create the encrypted key material (bin) file. 
      - Copy the material back 'aws s3 /ec2-path s://bucket --recursive'.

## Lab for KMS
- Create 3 users in 2 groups. Objective is to be able to share keys. One group is "administrator", second is "finance". Grant S3 full access policy to the Finance group. Also S3readAccess because they need to see the encryption keys.
- User A is the system admin. Users B and C are Finance users.  
- Console | Security Identity Encryption | KMS. Configure Keys. Symetric keys usually used with S3 and EBS. Key material origin is KMS.  Keys need a well defined alias and a description (comment). Note that you should tag keys!
- Next page is the Key Admin page. We don't actually want the AWS Admin have this ability. Instead, it should be a user. Note that you need to really think about giving the key admin the ability to delete the key ... insider? 
- Key usage permissions - users, AWS accounts. Review the JSON. 
- Create the bucket. Properties | Default Encryption. Can select none, S3, or KMS - select KMS and User B's master key.
- Login as User B. Note that B has 'read only".  Go visit S3. Upload a payslip.txt document. Upload a small text doc. 
- Review the file properties - looking for encryption. Then check see whow access. 
- Change the bucket to pbblic.
- Note that if you select the direct link to acccess the target source. 
- Now make the test file public - which will generate an 'invalid' argument because we are adding a layer. 
- Log out as B, login as C.
- Check KMS - we see user B's key. Attempt too key admins.  There should be an error message at the hop of page.
- For C's account - review IAM users area. If you attmept to add yourself as an adimn, you should get an error message at the top of page. 
- Net effect - User C can't mod the key or object.
- How about trying to change...

## Setup customer managed key
- Create alias, description, chose material option.
- Defined key administative permission - who has what access and manage the key
- Define key usage permissions - IAM user/role that can use, and how they can use, the key. 

## KMS Key Rotation Options (10/15/2020)
- Avoid reusing keys, instead rorating them on a regular basis. Regulatory may push a rotation cycle. 
- Methods vary based on the type of key in use - AWS Managed vs. customer imported.
- AWS Managed - will rotate every 3 years, and cannot change.  A new backing key is created, marked as 'active' for new reqeusts, while the old key is availabe for previously encryped file access. 
- Customer Managed - once per year, automatic but disabled by default. Can rotate on demand. Old keys can be deleted - which can be very dangerous. in KMS, go to customer managed keys. Create one, assign an admin, define key usage permissions. Rotation is a check box. 
- Customer Managed w/ imported key material - you must rotate these manually. 
- Process - import / buidl new, update applications, the new one will be the current key - prior is around to decrypt older data.  Update the aliases. 

## Customer Managed Key Pairs on Mac (Added 10/14/2020)
- EC2 has a Key Pairs link. You import the public key only. It gets a name, and you import the public key. Make 100% sure you know where the private key is.
- Linux Command: ssh-keygen -t rsa -b 2048 -> will generate two output files. 
- Then change permissions for linux, Mac - windows doesn't care.
- Windows Command: putty keygen w/ mouse movement for Randomness. Need to get the 64 bit installer.

## KMS and EBS (Added 10/16/2020)
- Services | Key Mgmt Services | Create Key. 
- EBS needs symetric keys. Select a solid name and add a tag.
- KMS Keys must have unique names for your account.
- Assign the key admin the approp usage permissions. 
- Then a named KMS key will be available in the EC2 Launch Wiz so you can select the named key on  Storage, step 3. Note 
- Note that you *cannot* copy a KMS key from one region to another.that there is a default KMS key for EBS named "aws/ebs". You can also add volumes and select your KMS key. To solve WRT EBS, stop the instance, copy the volume to a new region, and then encrypt in that region. 
- On a live EC2 instance:
  - You can stop an EC2 instance, then go into the root volume - still can't change encryption on a running system. 
  - To solve, you stop the instance and create a snapshot. (again - name it well). The snap shows up in the snap list. When you "copy", you can a) change the region and/or b) check the "Encrypt this snapshot" box, encrypt the volume, and then create a new VM based on the encrypted volume. 

## KMS Grants
- Alternative access control to the Key Policy. Key Policies are for relatively static definitions. 
- Programatically delegate use of CMK's to other principals - another user. Can only "grant" on a temp basis.
- Three commands
  - `aws kms create-key` - will give you an ARN.
  - `asc cli create-grant`
  - `aws cli list-grants`
  - `aws cli revoke-grant`
  - etc.

## Key Policy Conditions by Service
- Policy Conditions must be TRUE for the policy to take effect. May want to allow / deny based on reuqesting service. 
- KMS has a load of predefined condition keys. 
- Most Important: KMSViaService. Allow user to access when it comes from a specific service that *originated* the request.
- Effect the principle or ARN, resource is all, and the kms:ViaService option.

## Cross Account Access for Customer Master Keys
- Access is controlled using Key policy, IAM policy.  You can enable another account access, but you must enable cross account access. Two steps.
  - Acct A has a Customer Master Key. Acct B needs access to use the CMK (second uses CMK in first)
  - Change the key policy in A.  Select a key, on the details page there is an "add other accounts". Need the number.
  - Add IAM policy for users/roles in B. In the JSON - we give encrypt/decrypt/reencrypt to the resource by ARN in account A - so B needs the Acct ID and the key ID value (like a GUID). 

## EC2 and Key Pairs (Added 10/16/2020)
- When creating a Linux EC2 Instance you must create or specify a SSH key pair. They apper in the .ssh directory, in the authorized_keys file (type, key, name). Can "curl http://169.254.169.254/latest/meta-data/public-keys/0/openssh-key" for the default SSH pub key name and value. 
- From there, drop your keys onto the bucket. Use "ssh-keygen -t rsa", whcih will create a key and a key.pub. Add the key to the autorized_keys list - 'cat kepair.pub >> ../authorized_keys' (note that you do NOT use s single > sign!!!)  Note that you can attach and replace a role on the EC2 instance. Like adding access to S3 - and then use "aws s3 ls" to see buckets, and then copy new / updated keys to/from the bucket with 'aws s3 cp  filenames s3://path/direc' and the files will then be visible in the S3 area of the console. 
- You can delete a key pair from the AWS console. Must understand what happens if you breaka key pair.  If you look at the "curl http://169.254.169.254/latest/meta-data/public-keys/0/openssh-key" URL, it shows the key is present on the machine (but gone from the AWS console). Key pair name will be visible in EC2 machine details.  You can "clone" a running EC2 instance (Actions menu). In the EC2 create process, you can create a new key pair. Note that you will need to download the private key along the way. OS's keep the public key side of a key pair in tact as you clone them, or manipulate the key file. You just must have the private key. (this can be a real problem if someone keeps the Priv K, and you don't know this...)

# MarketPlace Security Products
- There are sec prod's in the AWS marketplace. Look for products that folow the CIS Security Benchmarks. 
- Variety of solutions are offered.  Be aware of different revenue models and licensing.

# AWS WAF and AWS Shield (Added 10/16/2020)
- WAF - Web App FW for HTTP/S forwarded to Cloud Front or an App Load Balancer. Controls access to content. URL decision making engine - disects query string parameters, and decides if it is allowed or not. (source=someging&a=b&evil=true_4 ...)
- On a block, WAF returns a 403 status code.
- AWS WAF integrates directly with Cloud Front or Application Load Balancers - nothing else in the AWS services world. 
- ALB's integrate w/ WAF at the regional level and Cloud Front at the global level.  Can actually protect sites not hosted in AWS (...) b/c CF supports custom origins outside of AWS.
- Three behaviors
  - Allow All except black listed = Black list
  - Block all except granted = White List
  - Count reuqests that match (analsys capability)
- Protection: IP, country, request header values, strings in requests, length of request, Presance of SQL code / query (looks for maliciousness), presance of a script
- Can create a WAF for a Cloud Formation Template (there is a small amoutn of cost if you use the template - only works in some regions)
- Cloud Formation Template (Mgmt Tools | Cloud Formation )
  - CF scripts infrastructure for you - provisions resources for you. These are called Stack Templates. "common-attacks.json"
  - You name the stack when you use it, an IAM role, parameters for advanced issues as well. Takes w ehile to setup (15 min on everage).  After your review and test you can disable CF Distrib. 
  - Services - WAF, WAF ACL's (Change filter to global), Cloud Front definition, App Load Balancer, WAF common attack pattern protection, Manual IP block set (/32, /24, /16 /8), Origin S3 bucket (must make that public - web content)
  - Need to add an association between the CF Distro w/ the WAF. To Test: once done, add your client IP, block it in the manual IP block set, and then you won't have access to content. 
- Shield
  - Should look over (Shield)[https://aws.amazon.com/shield/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc]
  - $3k for enterprise version - small biz likely just to use basic.

# EC2 Dedicated Instancs vs Dedicated Hosts  (Added 10/16/2020)
- Dedicated HW may share HW w/ other instances from the same AWS Acct which are not 'dedicated'.
. - Both types have dedicated HW (DI or DH). DI - share hardware w/ instances from your acct. DH give more visbility.
- Dedicated Hosts
  - Phys server dedicated to YOU. Provides more visibility / control of how instance are deployed to same server. 
  - Support using HW bound licenses 
  - Billed for the host
- Provisioning Notes
  - To provision: EC2 | Dedicated Hosts (left side). Select Instance type, and continue - doesn't take that long.
  - Can also provision a dedicated Instance inthe EC2 wiz as well. 

# Hypervisor Security and resource isolation (Added 10/16/2020)
- HyperVisor is a VM Monitor - Hosts and Guests. Idea is resource is shared to virt hosts.
- AWS Hypervisors are a mixture of Xen and Nitro. AWS created thier own Hypervisor w/ Nitro. All mograting there.
- HVM = Hardware VM.  (today, this is the preference). Windows EC2 can only be HVM.
- PV = lighter, Paravirtualization. 
- Guest has no elevated access to CPU - Host OS (Xen, Nigro) runs at Ring 0, for PV, EC2 run at Ring 1; applications operate at Ring 3.
- Isolation - there is a FW at the hypervisor layer which allows us to create Security Groups. Virtual interface sits on top of the Sec Grp. 
- Very few have access to Hypervisor; MFA is required. 
- Guest access - these OS's are controlled by the customer, we connect w/ SSH key pairs.
- Mem Scrubbing (disk and ram), EBS resets access when memory (RAM and Disk) is scrubbed. Not returned to pool until complete. 

# Microservices (Added 10/17/2020)
- Historically, applications were monolithic such that a change would require a large redeploy. Microservices solve that because they are small, specialized, focused, independent services that communicate over a well defined API. Modern applications are more likely to consist of small services running in a container (Docker). 
- Example: Cart, Recomendation engine, comment acceptance and posting, shipping, CC charge, user email messaging, shipping notification, ...
- Separating out services supports a much easier upgrade and scalability configuration.

# Containers (Added 10/17/2020)
- More like a virtual operating environment, with libraries, system tools/code, and language specific run time. Basically enough to run a micro service. Most often a Docker image. Docker images are run by the Docker engine.
- AWS has Elastic Container Service (ECS) and Kubernetes Service (EKS). Both can be deployed on EC2 instances. ECS is deeply integrated with other AWS services, wehreas EKS is Kubernetes conformant (benefits from FOSS community.)
- AWS Fargate is the preferred / recommended option. Fargate is 'serverless' and fully AWS managed (no need for a host OS)

## Best Practices for Containers (Added 10/17/2020)
- Avoid storing secrets on the container / code. Use AWS Secrets Manager instead. "Less is More".
- Use IAM roles instead of hard codeing credentials. 
- Don't run as the root account - create a service account. 
- Rule of thumb is to run a single service per container to minimize the container specific attack surface. 
- Trusted container sources only! Develop in house or use a trusted source. 
- AWS provides Image Scanning for containers in the Container Registry. Reports on identifiable CVE's. 
- Use an ECS endpoint interface to send traffic over the AWS private internet.
- If you need to use the public Internet, ensure that TLS is setup. This begs the question - where to store the certificate and the private key. Avoid dropping it in the Docker image, because thats a mgmt overhead. Limit of 4K in secrets manager / parameter store. Best is to AWS Certificate Manager (ACM). ACM is a single interface.  Read this (blog post)[https://aws.amazon.com/blogs/compute/maintaining-transport-layer-security-all-the-way-to-your-container-part-2-using-aws-certificate-manager-private-certificate-authority/].

## ECS Sample Application in the Console
- Console | Containers | Elastic Container Service. There is a get started button with a sample app provided (wizard, takes about 10 minutes). Creates a VPV, public IP, task definition for the Fargate cluster, no auto scaling, cluster, log group, uses a CloudFormation stack, two subnets, and a security group.  When done reviewing you can "Delete cluster."
-  To see the sample in action, get the public IP from the Tasks tab and hit the site.

# Creating a Custom VPC (Added 10/17/2020)
- Note the address range in the default VPC.
- Create:
  - VPC - Name, IP range, and don't click "dedicated".
    - Route Table will be created, but it won't be named.
    - A Network ACL is created, but it won't be named. 
    - A single security group is created as well, and it won't be named.
  - Subnets are next.
    - Name - Ideally you will have a naming convention = "Prv-10-0-1-us-east-1" might be a good one. Consider creating them on /24 boundaries for labs. 
    - VPC - Select the VPC it belongs to
    - AZ - which AZ will serve the subnet. Subnets cannot span AZs.
    - NOTE: in a subnet, you cannot use the first four ( 0, 1 for VPC router, 2 for DNS, 3 is reserved) and the last one (255) IP address.
  - Internet Gateway: Simple to create, you get one per VPC. Must separately attach a IGW to a VPC. The CLI command is `aws ec2 attach-internet-gateway --vpc-id "vpc-ID" --internet-gateway-id "igw-ID" --region us-east-1`
  - Attach the IGW to the route table: 
  - Create a specific route table. Avoid using the 'default'. If you don't associate subnets to a route table, they are automatically associated with the 'main' route table. Create a route table w/ a good name and attach it to your VPC.
  - Create a route out to the Internet. Edit the route table, add a route to 0.0.0.0. Select the target (there are several), and chose the IGW created above. Therefore any subnet that is assocaited w/ this one will have Internet Access. Select the subnet you intended to be 'public' to be associated w/ this route table. 
  - Enable Internet accessable subnet to get an auto-assigned public IP (subnets area Action). 
  - Test - setup an EC2 instance in priv and public subnets. 


# NAT Instances and Gateways (Added 10/17/2020)
- There are two types of NAT. Older are instances, newer are NAT GW's.
- Instances are an EC2 instance with updates to handle source rotuing - must disable the source / dest check.
- Gateways are created from the VPC.
- Creating a NAT GW.  
  - Select the Public Subnet. 
  - Create a new Elastic IP (there is a small charge for these)
  - Wait to edit the route table - it takes 10-15 minutes for a NAT GW to complete provisioning.
- After created, edit the route table.
  - In the route table, the 0.0.0.0/0 entry needs to point to the NatGW as the Target. 
- One key difference - a NAT Instance can be a Bastion server between the pub and priv subnets.

# NACL vs. Sec Groups (added 10/17/2020)
- NACLs have rule numbers for each rule which orders the rules. NACL's are first match out, lowest first.  Each subnet can only have one NACL, NACL's can have one or more subnets. 
- Emperically, the NACL controls inbound access to your VPC once it is associated with a subnet. Note that you need inbound access from, say, your IP to an EC2 server and response traffic via Ephemoral ports back outbound. 
- The default NACL allows inbound/outbound by default. Not so with a custom (or private) - deny only at create time.
- Rule numbers define the order, smaller integers to larger. 
- NACL's have inbound and outbound rules, each can control traffic. They are stateless, so if you want response traffic you need to permit ephemoral ports outbound for responses. This means you have to add 1024-65535 as an outbound in the ;output; rule in order to get response traffic back out through the NACL. This opens up response from any inbound permitted traffic. 
- One way to test - drop an inbound deny for a given port from your IP at a lower rule number than the 'allow' rule.

# Load Balancers and Custom VPC's (Added 10/19/2020)
- Three types - Application for HTTP/HTTPS and Network for TCP / UDP traffic. 
- Configure the load balancer through the wizard. We setup the LB for the VPC, and you must have two subnets into two public subnets for effecitveness. You get one subnet per AZ. 

# Elastic Load Balancers (ALB's) and TLS / SSL Termination (Added 10/19/2020)
- You can terminate the TLS/sSL session at the LB or the EC2 Host. If you term at the LB, data is forwarded to the EC2 host in clear text.  Effectively, the decryption overhead and TLS certificate are on the LB itself, with the effect that the EC2 instances aren't doing crytographic processing. Be aware that if you use the ALB as the Termination point to the EC2 system is not encrypted. 
- If you have a reason or some requirement to have encryption End to End (client browser to WebServer) then you need to use the Network Load Balancer w/ the TCP protocol on port 443 / 8443 / etc. The Classic LB is still available, but not recommeended. 

# VPC Flow Logs (Added 10/19/2020)
- Flow tuples between network interfaces to/from ENI's in the VPC. Can be created at three levels, which define how much data is collected. 1) VPC 2) subnet 3) interface. 
- To create: VPC | actions | create flow log. Can define a filter - the type of traffic (All, accept, reject). There is a role thats required - something like "FlowLogRole" works.  Logs go to a Destination Log Group, which are defined under Cloud Watch w/ an appropriate name. Once these are setup, you cannot change the definition. 
- Logs can be streamed to Lambda (which will run a lot of functions!)
- Can't setup a flow log for VPC's that are peered w/ your VPC unless both VPC's are in your account. No tagging yet.
- Not monitored: AWS DNS, Windows activation, 169.234 metadata, DHCP, and the AWS reserved IP's per subnet isn't logged. 

# NAT vs. Bastion Servers (Jump Boxes) (Added 10/19/2020)
- NAT handles Internet traffic, usually outbound.  Note that NAT Instances are on the way out. 
- Bastions are used for admin only. Idea is to have a single hardened Bastion, locked down, SSH and RDP from your main network only, use over a private network, that sort of thing. 

# Systems Manager Session Manager (Added 10/19/2020)
- Enables secure remote login to EC2 Instances. An alternative to using SSH and RDP. Browser Based using PowerShell or Bash, invoked from within the console, or the CLI / SDK.  Single solution for Linux and Windows.  No true SSH or RDP connection involved. No Bastion either. 
- Can be used for Phys/On Prem servers as well (hmmm). 
- Connections are fully auditable as well because you have centralized access control by user to specific or groups of instances. Logs come through Cloud Trail (session history). Keystroke logging is inclueded (wow) which can be sent to Cloud Watch and/or S3 buckets.
- You need a Role for SMSM to enable EC2 instances to communicate to SMSM. Service Role | EC2 Role | search for SSM, select AmazonEc2RoleforSSM. Launch an EC2 Instance w/ this role assigned.  Note: You cannot attach multiple IAM roles to a single instance (so if you want to use all of this cool AWS stuff... you will end up creating a Mega Role).
- To begin a session, in SSM, select the instance and start the session to get an interactive shell. 
- NOTE: On Linux, the SSM user starts w/ Root permissions by default. Once the log is written and the session is terminated, there will be a entry under "Totput Location" where you can review the output log - commands and output (so you have a recording of commands and results). 

# Systems Manager Parameter Store (Added 10/23/2020)
- Used to store confidential information. Idea is to store the data (license, credential, etc.) and control access to the paremter. 
- In the console, under EC2 under Shared Resources you will find parameter store. Sensitive data is stored, variety of access methods. You create a unique name, description, and the paramter itself. Parameters can be string, secure string, and string list (mult values, comma separated). Secure string is encrypted w/ a KMS key. 

# System Manager Run Command (Added 10/23/2020)
- Allws you to automate common tasks and ad hoc vonfig changes without having to login to each instance. Global machine interaction tool.
- Manageement Tools | Systems Manager or EC2 | Systems Manager. To get it to work, you will need a role and then apply the role to the instances. In the SSM portal, under Actions, hit "run command". There areseveral. Can add configuation in JSON, document the run event, and other options. At the bottom the run command shows you the AWS CLI command. 
- Commands can be applied based on tags, or selected manually. the SSM agent is in the Windows 2016 and other base images. 

# VPC End Points (Added 10/19/2020)
- Remember there are private network segments behind NAT GW's. VPC endpoints setup a network connection or a gateway for instances to communicate to AWS services. 
- In the console, create a Role for EC2. We want to allow EC2 instances to call AWS services. 
- Under Network and Content Delivery, you need to associate a subnet.
- IN the VPC dashboard, go to EndPoint. There are two types - Interface which create an ENI, or Gateways, which are HA.  Generally, use gateway. Associate the GW w/ the 'main' route table. Note that when using an endpoint you use private IP's not public IP's. You 'create', which will add an etry in the route table w/ a DNS like name (com.amazonaws.us-east-1.s3 as an example).

## VPC Clean Ups (Added 10/202020)
- Make sure that you enable Cost Explorer early in your lab use process. 
- For Labs: 
  - Remove Snapshots
  - Remove specialiezed services like Cloud HSM, NAT Gateway
  - Remove EC2 instances
  - Detach and Remove Internet Gateway
  - Delete any VPC endpoints
  - Delete any subnets
  - Check the billing / cost explorer page next day see if anything is stacking up a cost
- Optional
  - You *may* want to delete keypairs. Make sure that you know you have the private key if you chose to keep the Key Pairs

# AWS Cloud HSM (Added 10/19/2020)
- $1.45 / hr. For those of you doing labs, you can spend some dollars!
- Details: Single tenant, You control the keys, broad AWS support, supports Symmetric / asymetric (inlike KMS which is symmetric only), FIPS 140-2 and EAL 4 compliant.
- For labs, you will create a cluster. verify the HSM identitiy, launch an EC2 instance, load/config to client. ...
- Clusters can have systems in multiple AZ's. Once created, you *cannot* change the subnets! One Way Operation!
- For the Security Groups, you ned 2223 to 2225 inbound permitted for CloudHSM.
- To Initialize a cluster:
  - Click on the cluster ID and Initialize. Create the HSM in the cluster in private SubNet - takes a while.  Will assign an IP in the subnet. For ACG, there is an init-script - need to replace the cluster ID.  Need to download and sign a CSR from an EC2 instance. 
  - Need two certificates - Cluster CSR and the Issuing Certificate. These are generated froman EC2 image, where you need the CSR. You will use the CSR to generate a private key, create a self signed certificate, and then push both up to the Cloud HSM. *Do Not* lose the password you generate along the way! Name your files well so that you can upload the files back into AWS console for the CA certificate and the HSM certificate. 
  - For the client on EC2, need to get the 'cloudhsm-client-latest' file to have the AWS client package.  The pubkey needs to be dropped into the right location - /opt/cloudhsm/etc.  Connect to the cluster by using the private IP and the "cloudhsm_mgmt_util" script. 
  - Initialization then continues w/ logging in as the pre-crypto officer, updating the user/pass. Then login as the Crypto officer, and create some users. 
  - To import/export keys, you will need to use (generate and export) a "Wrapping key". 
  - When interacting with CloudHSM from the CLI, make sure you note the Key Handle ID as numerous commands require a specific key. 
  - Four user types: Precrypto Officer, Crypto Officer, Crypto User, Appliance User. 
  - NOTE: Passwords are non-recoverable, so you will have an availability outage should you lose the CloudHSM password that was used to gen up the system. 
  - Review the (HSM role chart)[https://docs.aws.amazon.com/cloudhsm/latest/userguide/hsm-users.html]
  
  ## Cloud HSM User Types (Added 10/19/2020)
  - Pre Crypto Officer (admin/password) - once changed, promo'd to Crypto Officer, then it dissappears. 
  - Ctypto Officer - Can manage user accounts. New users, password changes. Can't manage keys. 
  - Ctypto Users - manage keys: create, delete, share, import, export. Perform various cryptographic operations: sign, enc/decrypt.
  - Appliance User - cloning and synch operations. Exists on all 
  
  ## Cloud HSM Comamnds of Note (Added 10/19/2020)
  - loginHSM <role> <user> <pass>
  - listusers
  - changePswd
  - changePswd PRECO admin <passwd>
  - createUser <username> <passwd>
  - # service cloudhsm-client start 
  - genSymKey -t # -s # -l aes256 : this command will return a 'key handles'
  - genSymKey -t # -s # -sess -l export-wrapping-key
  - exSymkey -k # -out aes256.key.exp -w handle#
  - exportPrivKey -k handle# -out rsa2048.key.exp -w handle# :: will produce a PEM file
  - exportPubKey -k handle# -out rsa2048.pub.exp

## Clean up (Lab Tear Down) (Added 10/20/2020)
- Delete the EC2 instance you used w/ a terminate option.
- Services - find CloudHSM, delete the HSM from within the cluster. Wait.
- Delete the cluster itself. 
- Review the VPC - remove the associations and delete the auto-created security group.  Note you may need to update the Sec Grp itself and remove ref's.

# Amazon DNS and Custom VPC's (Added 10/20/2020)
- When you create a VPC, the VPC includes a DNS server. It uses a reserved IP in the CIDR range. For example 10.0.0.0/16, the .2 address will be the DNS server. 
- Can disable AWS DNS if you want: Network and Content Delivery | VPC. On the VPC ID there is an 'enabled' option. Click on the DHCP Option Set. This configures the AWS provided DNS. 
- From the VPC, Actions | Edit DNS resolution - uncheck 'enabled'. Save. 
- To have a new DNS server, you need to create a new DHCP option set, specify the DNS server (up to 4 IP's).

# Transit Gateway (Added 10/20/2020)
- Simplifies network management when you have multiple VPCs and on-prem netowork as well.  A service that allows you to use a centralized GW to talk to VPC's from the DC. Use when you have lots (100+) VPC's and you don't want to meticulously manage them.  You avoid managing point to point communications. 
- Assume you have multiple VPC's and a few different accounts, then the data center. Hub/Spoke. 
- TG sits between your data center and the VPC's. You use route tables to control what VPC's can communicate. 
- Much easiter to manage to/from VPC to data center. Also uses AWS private side network, not the public Internet. Oh, and its encrypted to boot. 
- Want more? ReInvent 2019 preso. 

## DDOS and Real World (Added 10/20/2020)
- DDoS - an attempt o exhaust a resource with network traffic. Specific methods include floods, half open scans, aplification/reflection attacks from ICMP/UDP services. 
- Attack Types
  - Half Open Scan: Exhausts connection pool, requiring timeout. Slowloris is an example.
  - Reflection Attack
  - ICMP Amplification Attack
- Mitigations
  - Minimze attack surface: Eliminate multiple access points wherever possible. Mitigation: Bastion / Jump Box with whitelisted connection IP's like your business network. Ideally, drop a B/JB in one VPC and permit that VPC to talk to other VPC's where resources reside. 
  - DDoS: Multiple requests at the same time, bring infrastructure to a breaking point (assumption is there is a stopping point). Mitigation: Scale horizontally and Vertically. Attackers must have a wider attack range to attack your resource range. 
  - Technucal App Attacks: Mitigation: Safeguard Exposed Resources. Cloud Front has GEO restriction (Should the Norks be able to talk to your website?). Use Origin access identity, users must be using CF URL's. Route 53: redirect to AWS CF distributions or different ELB w/ capacity, and of course WAF's which have L7 HTTP awareness and can interrogate/block specific URL's. Pricate DNS for internal resource names as well. 
  - Baseline: Understand what "normal" is for your usage pattern so you can understand spikes and their cyclical nature. This allows you to create an alarm for awareness. 
  - Having a plan for an attack.
    - Validate the Architecture design. 
    - You have a CBA for resiliancy tooling. 
    - AWS Shield is available at two levels. It is 'always on' flow based monitoring. 
      - L1: handles SYN/UDP floods, reflection attacks, some other session based attacks.
      - L2 @ 3k/mo: ELB protection, CloudFront / Route 53, handles more sophisticated attacks.

# Incident Response Scenarios (Added 10/20/2020)

## EC2 Hacked - What to do? (Added 10/20/2020)
- Recommended Process
  - Stop instance!
  - Snapshot the EBS volume. 
  - Deploy into an isolated VPC / Environment w/ no Internet connectivity.
  - Access using a forensic workstation (SANS SIFT, FSecure remote collection, book with Linux and mousnt the disk ...)
  - Read through original VPC logs (Flow, cloud watch, etc.)

## Leaked Credentials in Source Code Site (Added 10/20/2020)
- Assume that any exposure IS an exposure. 
- Process: From the Root User level, security credentials (upper right). (not in IAM)
- Find keys, mark them as inactive, create a new one, delete the old one.
- Same process for any exposed account. Not a bad idea if there is a remote possibility of other accounts as well.

## Reading Cloud Trail Logs (Added 10/20/2020)
- A traditional flow is: Start Time, Duration, Src-IP, Src-Port, Dest-IP, Dest-Port, protocol, bytes sent.  Some flow logs store bytes exchanged betwwn the two systems - should know the difference. 
- Flow log are stored in S3. Account+Region.
- Logs are KVP in JSON. Type, PrincipalID, arn, accountID, username, session, ... what occurred, when, etc.
- Effectively - any API call should be in a Cloud Trail log.
- Best Practice is to replicate to another account w/ another S3 bucket. 

# Penetration Testing in AWS Added 10/20/2020)
- AWS has a posted support policy for pen tests for a variety, but not all, services. Zome activies are prohibited. 
- Prohibited - DNS zone walk, port/protocol flooding, DDoS.

# Certificate Manager (Added 10/20/2020)
- Networking | Route 53: registered domains. It may take a bit. 
- Sec Compliance | Certificate Manager.  Need the name o/t domain. You can import mainstream certificates from other providers. There are two ways to validate. 1) DNS, proving you can validate 2). Email validation for the domain. Request and Confirm - then add the CNAME they asked for into the domain. Basically, prove that you can update the domain. 
- You can buy, auto renew, and extend domains in AWS.
- Amazon issued certicicates will auto renew. 
- Two services use AWS Certificates - Cloud Front distribution and Applicaion Load Balancer in the EC2 area. 
- You cannot export AWS Certificates - they are delivered at no charge, but you cannot use them elsewhere. 

# Securing Load Balancers with PFS (Added 10/20/2020)
- PFS: Perfect Forward Secrecy. Objective is that aquiring a future key does not jepardize a prior key. Alternately, if a key is compromised a year from now, you should not be able to read older data. (Worth reading the Wikipedia articles). Requires the "ECHDE-" TLS ciphers and the 2608 security policy. 
- You add a HTTPS listener (443/TCP). 

# API Gateway (Added 10/23/2020)
- API GW Throttling: You get a steady state of 10,999 / second, and if requests exceed that a "429 To Many Requests" message is returned to the client. Think of this as a DDoS mitigation technique. Furher limit of 5K burst across all API's in the account. If a client sends 10K in first milisecond, API GW servies 5K, then stops for the rest of the one second period.
- AWS support can increse the rate limit if desired. 
- What if you get identical requeests? Can reduece the number of calls to the end point. Caching is enabled by stage, API GW caches for a TTL count (up to 3600, 200 default).  If ttl=0, no caching.

# Compliance Frameworks (Added 10/23/2020)
- Main Three - PCI DSS, ISO 27001, HIPAA. Should read the 'compliance' page. ACG things PCI is the most important (Bah!)
- 27001:2005/10/13. Explains how to implement the ISMS.
- FedRAMP: Standardized approach for cloud services. 
- HIPAA: Easier for people to get health insurance, standardize claim codes, data exchange, and protect ePHI data.
- NIST: Numerous standard at NIST.gov.
- PCI DSS: Global standard, they don't care where you are ... protect debit, cash card, and credit card transactions.  (ACG class hit the Digital Dozen...)
- Others include SAS70, SOC-I, SOC-II.
- FIPS 140-2 and 3. KMS gets to L2, Cloud HSM gets to L3. 

# AWS Athena (Added 10/23/2020)
- Interactive Query service for data in S3, using standard SQL query syntax. You pay per query, per TB scanned. You don't need an ETL process. Can read a variety of data formats (CSV, etc.)
- Common use case: query log files stored in S3. Analyze AWS cost / usage reports which are usually in CSV. 

# AWS Macie (Added 10/23/2020)
- PII - Personally Identifiable Information. For exmaple, there is a (designated record set)[https://www.hhs.gov/hipaa/for-professionals/privacy/guidance/access/index.html] in the HIPAA domain that describes PHI and (PII)[https://www.osec.doc.gov/opog/privacy/pii_bii.html].  Simply: Name, home, DL number, tas-id, bank details, other sensitive informaiton that can tie back to an individual person.
- Macie uses natural language processing to discover, classify, protect sensitive information stored in S3. Can also use it to search for credit card data (specific digit patterns w/ an internal code check) to see if PCI mandaated data leaks. 
- Macie classifies by content type, file extension, theme, and regular expression. Theme's are interesting - AmEx, Visa, MC, banking, web exploitation tools, hacker tools, ...
- Macie protects data: instrument the system, analyze/classify data, report out to a dashboard or alert, provides visibility beyond a simple file name list, and it can analyze Cloud Trail to identify suspicious API activity. 
- Macie is in limited deployment, and not available in all regions. 
- Macie needs a service role defined in IAM. It needs permissions for S3 (create, read, delete) and CloudTrail (read, create). IAM role is built and applied when you push the "Enable Macie" button. 
- Best to use a faux file, drop it into an S3 folder, enable Macie, enable Macie for the account (you need to select the account) and your test bucket(s). There is also a Cloud Trail bucket created for Macie. 
- Extensive diagnostic dashoard is provided: classification, theme, source IP, etc. For 'findings;, you get the individual item and a summarization of the PII type. One super duper nice thing is you get Cloud Trail access for the data type. 

# GuardDuty (Added 10/23/2020)
- Machine Learning based service that looks for malicious behavior. Unusual API, malicious IP, attempts to disable logging, unauth deployments, EC2 compromised incidents. 
- Monitors Cloud Trail logs, VPC flow logs, DNS logs. 
- Gets threat intelligence data from well known third parties like ProofPoint, CrowdStrike.
- Response can be automated by triggering a Cloud Watch event, which can in turn trigger a Lambda function. 
- Takes 7-14 days to establish baseline. First 30d are free. Charge after that is based on event volume.
- Stored in Security, Compliance. Needs service permissions to analyze logs and a service role so it can retrieve instance metadata for EC2 instances. Effect is 'allow' to EC2 dsecribe instances / images. 
- Note - will need to use code to to cause behaviors (examcple script[https://github.com/awslabs/amazon-guardduty-tester]) The console has a way to generate sample findings though. 
- GD can have a white list for IP's and threat list of IP's you are OK with. 
- GD service will provide notification as the threat-scape changes. 
