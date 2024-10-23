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

AWS billing is based on a pay-as-you-go pricing model, meaning you only pay for the services and resources you use. AWS offers a variety of pricing models, payment tools, and features to help users manage and optimize costs.

AWS Budgets:

AWS Budgets allows you to set customized budgets for cost and usage tracking.
Alerts notify you when your actual or forecasted usage exceeds your budget thresholds.

Billing Dashboard:

The AWS Billing Dashboard provides an overview of your current and historical usage and costs.
Accessible from the AWS Management Console, it shows your monthly charges, forecasts, and cost breakdown by services and regions.

AWS Multi-Factor Authentication (MFA) is an additional layer of security for protecting your AWS account. It requires users to provide two forms of authentication: something they know (password) and something they have (an MFA device).

Benefits of MFA:

- Enhanced Security: MFA adds a layer of security by requiring users to present a second piece of information (typically a one-time code) in addition to their username and password.

- Protection from Unauthorized Access: Even if someone steals your password, they cannot access your account without the second factor (the MFA code).
























