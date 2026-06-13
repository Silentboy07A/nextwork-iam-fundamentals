# IAM Fundamentals using LocalStack

## Overview

This project demonstrates the fundamentals of AWS Identity and Access Management (IAM) using LocalStack.

The project focuses on creating IAM users, groups, and policies to manage access permissions following the principle of least privilege.

## Technologies Used

* AWS CLI
* LocalStack
* AWS IAM
* Docker

## Project Objectives

* Create an IAM User
* Create an IAM Group
* Create a Custom IAM Policy
* Add a User to a Group
* Attach a Policy to a Group
* Understand Role-Based Access Control

## Architecture

```text
IAM Policy
      │
      ▼
IAM Group
(nextwork-dev-group)
      │
      ▼
IAM User
(nextwork-dev-sakthi)
```

## Resources Created

### IAM User

| Property  | Value               |
| --------- | ------------------- |
| User Name | nextwork-dev-sakthi |
| Type      | IAM User            |

### IAM Group

| Property   | Value              |
| ---------- | ------------------ |
| Group Name | nextwork-dev-group |

### IAM Policy

| Property    | Value                        |
| ----------- | ---------------------------- |
| Policy Name | NextWorkDevEnvironmentPolicy |
| Type        | Customer Managed Policy      |

## Commands Executed

### Create IAM User

```bash
aws --endpoint-url=http://localhost:4566 iam create-user \
--user-name nextwork-dev-sakthi
```

### Create IAM Group

```bash
aws --endpoint-url=http://localhost:4566 iam create-group \
--group-name nextwork-dev-group
```

### Add User to Group

```bash
aws --endpoint-url=http://localhost:4566 iam add-user-to-group \
--group-name nextwork-dev-group \
--user-name nextwork-dev-sakthi
```

### Create IAM Policy

```bash
aws --endpoint-url=http://localhost:4566 iam create-policy \
--policy-name NextWorkDevEnvironmentPolicy \
--policy-document file://dev-policy.json
```

### Attach Policy to Group

```bash
aws --endpoint-url=http://localhost:4566 iam attach-group-policy \
--group-name nextwork-dev-group \
--policy-arn arn:aws:iam::000000000000:policy/NextWorkDevEnvironmentPolicy
```

## Concepts Learned

### IAM User

An IAM User represents an individual identity that can authenticate and access AWS resources.

### IAM Group

An IAM Group is a collection of users that share the same permissions.

### IAM Policy

An IAM Policy is a JSON document that defines permissions for AWS resources.

### Principle of Least Privilege

Users should only receive the permissions required to perform their tasks.

## Verification

Successfully verified:

* IAM User Creation
* IAM Group Creation
* User Membership in Group
* IAM Policy Creation
* Policy Attachment to Group



## Author

Sakthi B

Cloud Computing Student | AWS & Cloud Engineering Learner
