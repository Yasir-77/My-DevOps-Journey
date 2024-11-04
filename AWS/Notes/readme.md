# Chapter 1: AWS Introduction

## What is AWS?
Amazon Web Services (AWS) is a comprehensive and widely adopted cloud platform, offering over 200 fully-featured services from data centers globally. AWS enables businesses, developers, and individuals to access computing power, storage, databases, machine learning, and more over the internet, on-demand, and with a pay-as-you-go pricing model.

## AWS Cloud facts:

- In 2019, AWS had $35.02 billion in annual revenue.
- AWS accounts for 47% of the market in 2019 (Microsoft 2nd with 22%)
- Pioneer and Leader of the AWS Cloud Market for the 9th consecutive year.
- over 1,000,000 active users.

## AWS Cloud use cases:
- AWS enables you to build sophisticated, scalable applications.
- Applicable to a diverse set of industries.
- Use cases include: Enterprise IT, Backup and storage, Big sata analytics, Website hosting, mobile and social apps, Gaming

# Chapter 2: Global Infrastructure Introduction

## AWS Regions
- AWS has regios all around the world
- Names can be us-east-1, eu-west-2, etc.
- A region is a cluster of data centers
- Most AWS services are region-scoped

## How to choose an AWS Region
- Compliance with data governance and legal requirments: data never leaves a region without your explicit permission.
- Proximity to customers; reduced latency
- Available services within a region: new services and new features arent available in every region.
- Pricing: pricing varies region to region and is transparent in the service pricing range.

## AWS Availability Zones
- Each region has many availability zones (usually 3, min is 3, max is 6). Example: eu-west-2a, eu-west-2b,eu-west-2c
- Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity.
- Theyre seprate from each other, so that theyre isolated from disasters.
- They're connected with high bandwidth, ultra-low latency networking.

## AWS Points of presence (Edge Locations)
- Amazon has 400+ points of presence (400+ Edge locations & 10+ regional caches) in 90+ cities across 40+ countries.
- Contewnt is delivered to end users with lower latency


## Tour of the AWS Console
AWS has glocal services:
- Identity and access managment (IAM)
- Route 53 (DNS service)
- CloudFront (Content delivery network)
- WAF (WEB Application Firewall)

Most AWS services are Region-scoped:
- Amazon EC2 (Infrastructure as a service)
- Elastic Beanstalk (Platform as a service)
- Lambda (Function as a service)
- Rekognition (Software as a Services


# Chapter 3: Billing and MFA

## Billing
AWS billing is based on a pay-as-you-go pricing model, meaning you only pay for the services and resources you use. AWS offers a variety of pricing models, payment tools, and features to help users manage and optimize costs.

AWS Budgets:

AWS Budgets allows you to set customized budgets for cost and usage tracking.
Alerts notify you when your actual or forecasted usage exceeds your budget thresholds.

Billing Dashboard:

The AWS Billing Dashboard provides an overview of your current and historical usage and costs.
Accessible from the AWS Management Console, it shows your monthly charges, forecasts, and cost breakdown by services and regions.

## MFA
AWS Multi-Factor Authentication (MFA) is an additional layer of security for protecting your AWS account. It requires users to provide two forms of authentication: something they know (password) and something they have (an MFA device).

Benefits of MFA:

- Enhanced Security: MFA adds a layer of security by requiring users to present a second piece of information (typically a one-time code) in addition to their username and password.
- Protection from Unauthorized Access: Even if someone steals your password, they cannot access your account without the second factor (the MFA code).

MFA device options in AWS:

Virtual MFA device - Support for multiple tokens on a single device.

Universal 2nd factor security key - support for multiple root and IAM users using a single security key.

Hardware key fob MFA device - provided by Gernalto (3rd party)

Hardware key fob MFA device for AWS GocCloud (US) - Support for multiple tokens on a single device.

# Chapter 4: IAM
IAM stands for Identity and Access Management

## Users and Groups:
- Root account created by default, shouldnt be used or shared.
- Users are people within your organization, and can be grouped.
- Groups only contain users, not other groups.
- Users dont have to belong to a group, and a user can belong to multiple groups.

## IAM Permissions:
- Users or Groups can be asigfned JSON documents called policies.
- These policies define the permissions of the users
- In AWS apply the least privilege principle: dont give more permissions than the user needs.

## IAM Policies structure:
![image](https://github.com/user-attachments/assets/23bb2860-912b-414b-8ad6-cc66caea3fc0)

## How can Users access AWS:

To access AWS there are three options:
- AWS management console: protected by password + MFA
- AWS command Line Interface (CLI): protected by access keys
- AWS Software Developer Kit (SDK) for code: protected by access keys

Access keys are generated through the AWS Console

Users manage their own access keys, access keys are a secret just like a password.
- Access Key ID = Username
- Secret access key = Password

### What's the AWS CLI:
- A tool that enables you to interact with AWS services using commands in your command-line shell.
- Direct access to the public APIs of AWS services i.e S3 buckets
- Can develop scripts to manage your resources.
- Its open-source
- Alternative to using AWS Management Console.

### What's the AWS SDK:
- AWS Software development Kit (AWS SDK)
- Lanuage specifiC APIs (set pf libraries)
- Enables you to access and manage AWS services programmatically
- Embedded within your application]
- supports: SDKs (i.e Javascript, P[ython, PHP), mobile SDKs (i.e. Android, IOS), IoT Device SDKs (Embedded C, Arduino)
- Example: AWS CLI is built on AWS SDK for python AWS SDK

## AWS IAM roles for services:
In AWS Identity and Access Management (IAM), roles are a way to delegate permissions to services and applications running on AWS, allowing them to perform specific tasks without the need for hard-coded credentials. 

IAM roles are especially useful when services like EC2, Lambda, or ECS need to interact with other AWS services (like S3, DynamoDB, or RDS) on behalf of users.

## IAM security tools:
- IAM Credentials report (account level) - A report that lists all your accounts users and the status of their various credentials.
- IAM Access advisor (user level) - Access advisor shows the service permissions granted to a user and when those sevices were last accessed. This informartion is use to revise policies.

# Chapter 5: Amzanon Compute

## EC2

EC2 = Elastic Compute Cloud = Infrastructure as a service.

EC2 is one of the most populaar of AWS offerings, It mainly consists in the capability of:
- Renting virtual machines (EC2)
- Storing data on virtual drives (EBS)
- Distributing load across machines (ELB)
- Scaling the services using an auto-scaling group (ASG)

Knowing EC2 is fundamental to understand how the cloud works.

### EC2 sizing & configuartion options

- Operating System (OS): Linux, Windows or Mac OS
- How much compute power & cores (CPU)
- How much random-access memory (RAM)
- How much storage space: Network-attached (EBS & EFS), hardware (EC2 Instance Store)
- Network card: speed of the card, Public IP address
- Firewall rules: security group
- Bootstrap script (configure at first launch): EC2 User Data

### EC2 User Data

- It is possible to bootstrap our instances using an EC2 User data script. Bootstrapping means launching commands when a machine starts
- That script is only run once at the instance first start
- EC2 user data is used to automate boot tasks such as: Installing updates, Installing software, Downloading common files from the internet
- Any automation task you want to run on your machine when it first loads up.
- The EC2 User Data Script runs with the root user

### EC2 Instance types 

Different types of EC2 Instances:
- General Purpose
- Compute Optimized
- Memory Optimized
- Storage Optimized
- HPC Optimized
- Accelerated Computing

#### Basic Format of EC2 Instance Types

The naming convention for an EC2 instance type typically follows this pattern:

<Family><Generation>.<Size>

For example: m5.large, t3.micro, c5.2xlarge

Breakdown of the Naming Convention Components

1. Instance Family (e.g., m, t, c, r, p, etc.):

This indicates the primary use case or performance characteristic of the instance. Different families are optimized for specific workloads:

| FAMILY CODE  | PURPOSE  | 
|-------|------|
| t  | General purpose |
| m | General purpose | 
| c | Compute Optimized   | 
| r | Memory Optimized   |
| i | Storage Optimized   |
| p | Accelerated Computing   |

2. Generation (e.g., 5, 6, etc.):

The generation number represents updates to hardware and capabilities within each family.

Each subsequent generation improves on performance, networking, and sometimes pricing (e.g., m5 is the fifth generation of m family instances).


3. Size (e.g., large, xlarge, 2xlarge, etc.):

This suffix defines the virtual CPU (vCPU) count and memory size. Size often determines the amount of compute power (CPU cores) and memory provided by the instance type.

Sizes generally scale in the following progression (though some families have additional or fewer options):
nano < micro < small < medium < large < xlarge < 2xlarge < 4xlarge < 8xlarge < 16xlarge < 32xlarge





  





























