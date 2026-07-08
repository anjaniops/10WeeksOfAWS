# 🔐 Day 4 – IAM Hands-On Lab

## Overview

Today I practiced AWS IAM by creating users, groups, and policies while following the Principle of Least Privilege. I also created a custom IAM policy for a single S3 bucket and verified the permissions through hands-on testing.

## Tasks Completed

### ✅ Lab 1 – S3 Read-Only Access

- Created `S3ReadOnlyGroup`
- Attached `AmazonS3ReadOnlyAccess`
- Created `learner-s3`
- Verified read access to the `anjani-demo` bucket
- Verified upload and delete operations were denied

### ✅ Lab 2 – EC2 Read-Only Access

- Created `EC2ReadOnlyGroup`
- Attached `AmazonEC2ReadOnlyAccess`
- Created `learner-ec2`
- Verified EC2 dashboard access
- Verified launch and terminate actions were denied

### ✅ Lab 3 – Billing Read-Only Access

- Created `Billing` group
- Attached `AWSBillingReadOnlyAccess`
- Created `learner-billing`
- Verified Billing Dashboard access
- Confirmed no access to manage other AWS services

### ✅ Lab 4 – Custom S3 Read-Only Policy

- Created `CustomS3ReadOnlyTrainingPolicy`
- Restricted access to the `anjani-demo` bucket
- Attached the policy to `CustomS3ReadOnlyGroup`
- Added `learner-s3` to the group
- Verified read access
- Verified upload and delete were denied

## What I Learned

- Creating IAM users and groups
- Using AWS managed policies
- Creating customer managed policies
- Applying the Principle of Least Privilege
- Restricting access to a specific S3 bucket
- Testing IAM permissions using real **Access Denied** errors

## Status

✅ Day 4 completed successfully.
