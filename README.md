# CICD-Activity-2
# Role-Based Access Control using AWS IAM for EC2 Management

## 📌 Overview
This project demonstrates how to implement **Role-Based Access Control (RBAC)** for Amazon EC2 using **AWS Identity and Access Management (IAM)**.  
You will create IAM user groups, attach AWS managed and custom policies, add IAM users, and test the permissions using the IAM login URL.

---

## 🛠️ Objectives
- Create IAM User Groups for EC2 (Admins, Operators, Viewers)
- Attach AWS Managed Policies
- Create a Custom IAM Policy
- Assign IAM Users to Groups
- Test Permissions of Each User

---

# 🪜 Steps to Implement RBAC for EC2

## 1. Open AWS Console
- Log in to your **AWS Free Tier account**
- From AWS Console Home → Open **IAM**

---

## 2. Create IAM User Groups

### 🔹 Group 1: EC2-Admins1
1. IAM → User groups → **Create group**
2. Name: `EC2-Admins1`
3. Search and attach: `AmazonEC2FullAccess`
4. Click **Create group**

---

### 🔹 Group 2: EC2-Operators1
1. Create another group named: `EC2-Operators1`
2. Do **not attach any policies** yet

---

### 🔹 Group 3: EC2-Viewers1
1. Create group named: `EC2-Viewers1`
2. Attach: `AmazonEC2ReadOnlyAccess`
3. Create the group

---

## 3. Create a Custom IAM Policy

1. IAM → Policies → **Create policy**
2. Select **JSON**
3. Paste any custom operator EC2 policy you prepared
4. Click **Next**
5. Name it: `ec2-operator-policy`
6. Click **Create policy**

---

## 4. Attach Custom Policy to EC2-Operators1

1. IAM → User groups
2. Select `EC2-Operators1`
3. Go to **Permissions**
4. Click **Attach policies**
5. Search for `ec2-operator-policy`
6. Select it → **Attach policies**

---

## 5. Create IAM Users

### 👤 AdminUser1
1. IAM → Users → **Create user**
2. Username: `AdminUser1`
3. Enable console login
4. Set **Custom password**
5. Add user to group: `EC2-Admins1`
6. Click **Create user**

---

### 👤 OperatorUser
1. Create user `OperatorUser`
2. Enable console login → Custom password
3. Add to group: `EC2-Operators1`
4. Create user

---

### 👤 ViewerUser
1. Create user `ViewerUser`
2. Enable console login → Custom password
3. Add to group: `EC2-Viewers1`
4. Create user

---

## 6. Test IAM User Access

1. Go to **IAM Dashboard**
2. Copy the **IAM User Sign-in URL**
3. Open it in a new tab
4. Log in as `AdminUser1`  
5. Reset password → Continue

### AdminUser1 can:
- Start EC2 instances
- Stop EC2 instances
- View all EC2 settings  
(Some actions fail if instance is not in a valid state — expected behavior)

Repeat the same for:
- `OperatorUser`
- `ViewerUser`

---

# 🎉 Completed: RBAC for EC2 using AWS IAM
This project successfully demonstrates how to implement Role-Based Access Control for EC2 using IAM groups, policies, and users.


