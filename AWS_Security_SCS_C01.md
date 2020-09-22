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
- Need to know how to manage IAM and how IAM Policies relate to other services.
- Controlling access to "root": Preserve Keys, enable MFA, create secondary admin accounts, 
- IAM: Central control of users (people), groups (of users), roles (often assigned to EC2 and other services). policies (applied to groups who then inherit). Password policies. Share access. Granular perms. Identity Federation. Setup MFA. Temp access grants. 
- Supports many regulatory, rqmts. 
- Policy - a JSON DOC with a specific grant for specific rights to a AWS service.
- IAM policy conflict
- IAM UI Review Notes
-- 
# Cloud Trail


