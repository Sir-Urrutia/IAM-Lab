# AWS IAM Project: Managing Users, Groups, and Permissions

## **Objective:**
This project demonstrates how to manage **IAM users, groups, and permissions** in AWS to control access to resources like **EC2** and **S3**. The goal of the project was to practice creating IAM users and groups, assigning permissions, and testing how policies affect access to resources.

---

## **Steps Completed:**

### **1. Created IAM Groups**
- **`S3-Support`**: Read-only access to S3 (using `AmazonS3ReadOnlyAccess` policy).
- **`EC2-Support`**: Read-only access to EC2 (using `AmazonEC2ReadOnlyAccess` policy).
- **`EC2-Admin`**: Full access to EC2, including starting and stopping instances (custom **inline policy**).

### **2. Created IAM Users**
- **`user-1`**: Assigned to the **`S3-Support`** group for read-only access to S3.
- **`user-2`**: Assigned to the **`EC2-Support`** group for read-only access to EC2.
- **`user-3`**: Assigned to the **`EC2-Admin`** group for full access to EC2.

### **3. Assigned Permissions**
- Assigned the appropriate **managed policies** to each group.
- Created a **custom inline policy** for `EC2-Admin` to allow full access to EC2 actions like `DescribeInstances`, `StartInstances`, and `StopInstances`.

### **4. Tested Permissions**
Each user was signed in via the **IAM user sign-in URL** to test their permissions:
- **`user-1`** (S3-Support): 
  - Successfully viewed **S3 buckets** (read-only).
  - Was **not able** to access or modify EC2 resources.
  
- **`user-2`** (EC2-Support): 
  - Successfully viewed **EC2 instances** (read-only).
  - Was **not able** to access S3 resources.

- **`user-3`** (EC2-Admin): 
  - Successfully started and stopped EC2 instances (full access to EC2).
  - Was **not able** to access S3 resources.

---

## **Key Concepts Learned:**
- **IAM Groups**: Groups are useful for assigning permissions to multiple users at once.
- **Managed Policies vs. Inline Policies**: Managed policies are reusable and apply to multiple users/groups, while inline policies are specific to one user/group.
- **Testing Permissions**: By signing in as users with different permissions, we can verify that each user has the right level of access.

---

## **Conclusion:**
This project successfully demonstrates the creation and management of IAM users and groups to control access to AWS resources. Through this exercise, we learned how to configure policies to enforce permissions and test access levels for different user roles.

## Screenshots
### 1. Creating IAM Groups EC2 Support & S3 Support
![S3-Support](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/4S3Group_Naming.png?raw=true)
---
![EC2-Support](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/3EC2Group_Naming.png?raw=true)
### 2. Custom Inline policy for EC2-Admin
![EC2-Admin Policy](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/5EC2_Admin.png?raw=true)
---
![Creating Policy](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/7EC2_Policies.png?raw=true)

### 2. Creating IAM Users and assign to groups
![Creating Users](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/9User_1.png?raw=true)
---
![Assigning user to group](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/10User_assign.png?raw=true)
---
![Assigned all three Users](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/11Assigned_users.png?raw=true)

### 3. Tested Permissions
![EC2-Admin](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/17U3_EC2_inline.png?raw=true)
![Admin Failed access](https://github.com/Sir-Urrutia/IAM-Lab/blob/main/screenshots/18U3_failed_access.png?raw=true)

