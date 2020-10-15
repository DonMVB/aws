- [Basics - Terms and Foundations](#basics---terms-and-foundations)
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
  - Multi tennant Managed service that makes it easy to create/control encryption keys. To separate, Uses HSM's.
  - Users can protect thier data by being issued keys. 
  - KMS is region based!
  - Group: AdministratorAccessPermission
  - S3:
    - We can see encryption in use on KMS. Won't work with anonymous access.
    - From within the AWS console, auth'd users can open files b/c users have access to the key. 
    - Users can also download.
  - IAM - how can you make access more secure?
    - Can grant access to keys, like we can grant admin access to a given key. 
    - Can grant "key user" access. 
    - Changing a group (like full access to SystemAdministrator) assigns a subset of access. For KMS, there are common usage capabilities. 
  - Key delete 
    - Can't directly delete. Instead, can schedule a key for delete - minimum 7d wait. (protection period). Key is marked as "Pending Deletion".
    - Can create a cloud trail + alert + SNS notification to see these though. 
    - Once a key is pending deletion, you will get errors upon any file access attempt. 
    - Root User can cancel key deletion, which will leave the key as disabled. Must specifically enable. 
  - RNew EC2 instance
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
