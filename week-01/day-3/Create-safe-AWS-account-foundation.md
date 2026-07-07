# Day 3 - Account Security Lab

## Goal
Build a secure AWS account foundation by following AWS security best practices.

---

## Lab 1 - Secure Root User

### Tasks Completed

- ✅ Logged in to the AWS Root account
- ✅ Enabled Multi-Factor Authentication (MFA) for the Root user
- ✅ Created an IAM Administrator user: `anjani-admin`
- ✅ Stopped using the Root account for daily AWS activities

### Why should the Root User not be used daily?

The Root user has unrestricted access to every AWS service and resource. Using it for routine tasks increases the risk of accidental changes or security breaches. AWS recommends using IAM users or roles for everyday administration and reserving the Root account for account-level tasks only.

### Evidence

- Screenshot: Root MFA Enabled
- Screenshot: IAM Admin User Created

---

## Lab 2 - Billing Alert

### Tasks Completed

- ✅ Opened the AWS Billing Dashboard
- ✅ Created a Cost Budget
- ✅ Configured an email notification for budget alerts

### Why monitor billing from Day 1?

Billing alerts help detect unexpected charges early and prevent unnecessary costs while learning AWS. They encourage responsible cloud usage and cost awareness.

### Evidence

- Screenshot: AWS Budget Created
- Screenshot: Budget Alert Configuration

---

## Key Takeaways

- Never use the Root user for daily work.
- Always enable MFA on the Root account.
- Use an IAM Administrator user for routine management.
- Configure billing alerts before creating cloud resources.
- Security and cost management should be implemented from the beginning.

---

## Environment

| Item | Value |
|------|-------|
| AWS Region | US East (N. Virginia) - us-east-1 |
| IAM Admin User | anjani-admin |
| Root MFA | Enabled |
| Billing Budget | Configured |