# AWS IAM Role Management with S3 List Bucket Permissions for EC2

This guide will walk you through creating an IAM role that grants EC2 instances the permission to list S3 buckets. We will verify the functionality by checking the EC2 instance's ability to list S3 buckets before and after attaching the role.

## Steps

### 1. Create IAM Role

1. **Navigate to IAM Roles**
   - Sign in to the AWS Management Console and open the IAM console at https://console.aws.amazon.com/iam/.
   - In the navigation pane, choose **Roles**.
   - Click on **Create role**.

   ![Create IAM Role](https://github.com/user-attachments/assets/669848ad-a785-40c5-8b3e-ec7441d01c97)

2. **Select AWS Service**
   - Under **Select trusted entity**, choose **AWS service**.
   - Select **EC2** from the list of services.
   - Click **Next**.

   ![Select AWS Service](images/select-aws-service.png)

### 2. Attach Permissions Policy

1. **Attach Permissions**
   - In the **Attach permissions policies** section, search for `AmazonS3ReadOnlyAccess`.
   - Select the `AmazonS3ReadOnlyAccess` policy.
   - Click **Next**.

   ![Attach Permissions Policy](images/attach-policy-1.png)

### 3. Configure Role

1. **Name and Configure Role**
   - Enter `S3ListBucketRole` for the **Role name**.
   - Optionally, add a description and tags.
   - Click **Create role**.

   ![Configure Role](images/configure-role.png)

### 4. Attach Role to EC2 Instance

1. **Modify IAM Role for EC2 Instance**
   - Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
   - In the navigation pane, choose **Instances**.
   - Select the instance you want to attach the role to.
   - Click on **Actions**, then **Security**, and then **Modify IAM role**.
   - Choose `S3ListBucketRole` from the **IAM role** list.
   - Click **Update IAM role**.

   ![Attach Role to EC2 Instance](images/attach-role-to-instance.png)

### 5. Verification

#### Verify EC2 Instance Cannot List S3 Buckets (Before Attaching Role)

1. **Connect to EC2 Instance**
   - Connect to the EC2 instance using SSH or Session Manager.
   - Run the following command to attempt to list S3 buckets:

   ```bash
   aws s3 ls
