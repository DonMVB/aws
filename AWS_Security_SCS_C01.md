- [Basics - Terms and Foundations](#basics---terms-and-foundations)
  - [Security In AWS](#security-in-aws)
- [IAM (Recap from SAA C02 to Security)](#iam-recap-from-saa-c02-to-security)
  - [IAM Policy Review](#iam-policy-review)
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
- [Cloud Trail](#cloud-trail)

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

# IAM (Recap from SAA C02 to Security)
- Need to know how to manage IAM and how IAM Policies relate to other services. Can't be managed by a "PowerUser", only an "Admin" user. 
- Controlling access to "root": Delete (preserve) Keys, enable MFA, create secondary admin accounts.
- IAM: Central control of users (people), groups (of users), roles (often assigned to EC2 and other services). policies (applied to groups who then inherit). Password policies. Share access. Granular perms. Identity Federation. Setup MFA. Temp access grants. 
- Supports many regulatory, rqmts. 
- Policy: A JSON DOC with a specific grant for specific rights to a AWS service. Created via the Visual Editor, can review the JSON doc as well. Always use `Principle of least privilege`.
- Example: Create a user, give them "S3 Full" only, and they should have access to see just S3 content and then denied to other services (splash screen/dash w/ no data thought). Try to create an S3 policy for "read/write", not "bucket create".
- IAM policy conflict resolution (IAM therapy?)
- Tips: Global, 3 policy types (AWS managed, customer managed, inline), 

### IAM UI Review Notes
- Security Status quick check - Delete Root keys,
- My Sec Credentials UI
- User Sec Creds: Password, add MFA (can deactivate and then re-activate for a refresh), 
- Virtual MFA: You should make a screen shot of the QR code!

## IAM Policy Review
- Specify what you amy do with an AWS resource. Applied to user, group, role. Or what can a priciple do in AWS.
- Three types: AWS managed, customer, inline.  Policy names are links to JSON objects. 
- AWS Managed: Shared across AWS, who defined them. Can change occassionally (usul. minor). Read Only, Admin, etc. Indicated with yellow box icon.
- Admin user: everything but billing.
- PowerUser: everything but IAM and changes in there.
- Customer Managed: Standalone, in an AWS account, then can be applied. Can cut/paste across accounts, can't "send over". 
- Inline: Strict 1:1 relationship between policy and its entity. Very directed. 
- Path: Console: Security and Compliance -> IAM. User | Group - attach policy during creation. 

### Polcy Doc Notes
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
- 

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
- CRR does work across accounts. IAM role must have permissions in the DEST bucket, which requires CRR and a role. Can also change the ownership to the dest bucket owner during replication. Can be applied to Cloud Trail audit logs for enhanced security - replicate the source CT Logs to a dest, so they can't be touched as the owner changes to dest on replication. (Powerful IR prep action.)
- What is replicated? New items as they are added only. Will replicate unencrypted, and follow rules for encrypted. Metadata. ACL Updates. Tags. Objects w/ read + read ACL permissions. 
- Deletes: the delete marker is replicated, but underlying versions are not there.
- Not replicated: Objects encrypted w/ Server Side Encryption (customer supplied keys). Deletes to a particular version. 
- Encryption rules: SSE-S3, SSE-KMS. Need to explicitly enable KMS key encryption. 

## Securing S3 using CloudFront (Added 9/29/2020)
- You can force a user to use a CloudFront URL for an underlying S3 bucket. Remember, there is a cost to CloudFront.
- Network | CloudFront: When you create a distribution, it can take up to 15 minutes for the dist to be global.
- To use a custom TLS Certificate, you need to import a certificate via Amazon Certificate Manager (ACM). Not the same as a load balancer certificate (no borrowing).

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
- Federation: Combining or joining users from Domain A w/ Domain B.  Handled by an Identity Broker. Each side has an Identity Store. Identity = user. 
  - Active Directory
  - SAML Assertion
- Example: An IPSEC VPN joins campus to AWS resources. A web app in AWS can auth against on-prem AD. Any app can ask an "Identity Broker" against an LDAP to validate identity. The identity Broker calls GetFederationToken using IAM creds w/ the IAM policy + duration, and grant policy. STS validates these. STS returns an access key, secret access key, token, and token lifetime duration.  Applications can further pass down the STS token on behalf of the user. 

# Cognito, a Web Identity Federation (Added 9/29/2020)
- WIF allows us to give temp AWS creds after someone has authenticated with well known web-ID providers. Users get an auth code (JWT). Third parties must support / provide Amazon Cognito.
- Amazon Cognito: Sign up / Sign In, server "guests", is an ID Broker, Synch up data on mobile, recommended for mobile apps and AWS services.

## Cognito User Pools 
- User Pools - Directories used to manage sign in / sign up.  Successful auth gen's up JWTs (the authentication piece.)
- Identity Pools enable us to create unique IDs for users. More to do with assigning roles to users who have already authenticated (the authorization piece.)

## Lab: Cognito User Pool (Added 9/29/2020)
- Console | Security Identity | Cognito.
- Manage User Pools, Create w/ a usable name. Most of the defaults are OK. 
- Add an App Client - again, need a usable name.  This is used to call API's on our behalf. Cofigure the app client, which will be Cognito user pools. The Callback user pool will be where users are redirected back to once successfully auth'd. There is also a sign up URL. ON OATH - Check both Auth Grant and Implicit Grant (provides the JWT). Normally will also check all OATH scopes. 
- Create a domain name as a prefix for Cognito, added to `.auth.region.amazoncognito.com`.
- The sign in and sign up pages can be customized (UI makes this fairly easy).
- Under App Integration, get the name. Need to add some params - /login?response_type=token&client_id= and you need the App Client ID - and then some more params b/c you are generating a one-off URL. Will get a sign up / sign in page. (actually kinda nice!)
- The site also can send (and you should send) an end user verification code. 

# Cloud Trail
