- [Basics - Terms and Foundations](#basics---terms-and-foundations)
  - [Security In AWS](#security-in-aws)
- [IAM (Recap from SAA C02 to Security)](#iam-recap-from-saa-c02-to-security)
  - [IAM Policy Review](#iam-policy-review)
- [S3 Bucket Policies (Added 9/29/2020)](#s3-bucket-policies-added-9292020)
  - [Lab (Added 9/29/2020)](#lab-added-9292020)
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
- Specify what can / cannot be done on a bucket by user. Ann can create, Joe can delete.
- Can grant cross account access for other acconts to read/write bucket.
- Can solve for size limits. IAM policies = 2 KB for users, 5KB for groups, S3 bucket policies = 20 KB.
- Practically, it is often easiter to manage Access Control at the bucket level than to work w/ IAM policies and apply them.
  - Easier to grant a "Allow 3, deny all else" policy.
- All S3 access is blocked to 'public' by default (AWS answer to bad user mgmt.)

## Lab (Added 9/29/2020)
- Create two buckets and two IAM users. By S3 policy, deny a user from read/write but allow them via IAM policy.
- Console | S3, Create buckets. S3 | Permissions | Access Control List.   S3 | Permissions | Bucket Policy. Copy ARN. 
- IAM | User - grab users ARN. 
- Use the Policy Generator. Principle = ARN o/t User. Actions - allow user to "delete".  Get the S3 ARN. Add Stmt if you want more. Review the JSON. 
- Can paste in the JSON - will get an arror. Need to give a direction, which would be /* for the entire bucket.
- Create a second S3 bucket. Test user A and B "PUT" on the second bucket. Then test User A & B Put in the First bucket. An error should appear in ... ?


# Cloud Trail


