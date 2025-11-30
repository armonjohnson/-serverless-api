# 🔨 Serverless API — AWS Lambda, API Gateway & S3

## B — Background  
This project was completed as part of an AWS Training & Certification hands-on lab.  
The goal was to build and deploy a serverless API using AWS Lambda, API Gateway, S3, and the AWS Serverless Application Model (SAM).  
After deployment, the Lambda function was updated to dynamically read and return the contents of an S3 object.

---

## U — Understanding

### Architecture
Client → API Gateway → Lambda → S3

yaml
Copy code

### AWS Services Used
- AWS Lambda  
- Amazon API Gateway  
- Amazon S3  
- AWS CloudFormation  
- AWS SAM  
- IAM  

### Architecture Diagram  


---

## I — Implementation

### 1. Build & Deploy
Commands used:
```bash
sam build
sam deploy --guided
Created CloudFormation stack

Deployed Lambda + API Gateway

Retrieved API URL from stack outputs

2. Initial Testing
Tested API using browser & curl:
Lambda returned placeholder response:

arduino
Copy code
"These are not the contents you are looking for."
3. Update Lambda
In app.py, replaced:

python
Copy code
contents = "These are not the contents you are looking for."
with:

python
Copy code
contents = obj["Body"].read()
4. Redeploy
bash
Copy code
sam deploy
5. Final Testing
API returned actual S3 object content:

arduino
Copy code
"Welcome to AWS Lambda!"
L — Lessons Learned
How AWS SAM builds and deploys serverless applications

How API Gateway triggers Lambda functions

Understanding IAM permissions for S3 access

CloudFormation stack updates and outputs

Debugging Lambda functions and S3 reads

Testing APIs via curl and browser

D — Demo / Deliverables
All screenshots of:

Lambda function (before/after)

S3 bucket & object

SAM deploy output

CloudFormation stack outputs

API testing (curl & browser)

Lab completion screen
