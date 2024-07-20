# AWS IAM User and Group Management

This guide will walk you through creating IAM users, creating groups, attaching policies to those groups, and adding users to groups using the AWS Management Console.

## Steps

### 1. Create IAM Users

1. Sign in to the AWS Management Console and open the IAM console at https://console.aws.amazon.com/iam/.
2. In the navigation pane, choose **Users** and then choose **Create user**.

![Create IAM User](https://github.com/user-attachments/assets/81ca8a6b-19db-455e-b989-dffa02e9d626)
   
3. For **User name**, enter `John`. Select the checkbox next to **AWS Management Console access**, then choose **Next: Permissions**.

![Create IAM User](https://github.com/user-attachments/assets/45b9bac7-8cde-41aa-9a0a-62516d3a914a)

4. Repeat the steps for another user, `Jenny`.

![Create IAM User](https://github.com/user-attachments/assets/bb2aa274-2d48-48b7-8f43-e6164c3fea00)

### 2. Create IAM Groups

1. In the navigation pane, choose **User groups**, and then choose **Create group**.

![Create IAM Group](https://github.com/user-attachments/assets/8117c1bb-b85e-4574-82ed-890e05e6cd04)
   
2. For **User group name**, enter `EC2`. Choose **Create group**.

![Create IAM Group](https://github.com/user-attachments/assets/28fdb3ab-8c99-4007-8596-f2a16ab8e75b)

3. Repeat the steps for another group, `S3`.

![Create IAM Group](https://github.com/user-attachments/assets/9eb9afd4-2d85-4f77-b600-135e1f40028e)

### 3. Attach Policies to Groups

1. In the navigation pane, choose **User groups** and then select the `EC2` group.

![Create IAM Group](https://github.com/user-attachments/assets/aa114fda-0e27-4685-a1d4-3cce08beef76)

2. Choose the **Permissions** tab, and then choose **Add permissions**.

![Create IAM Group](https://github.com/user-attachments/assets/6ec8fc00-d839-4859-b937-3349ac76ddb3)

3. Choose **Attach policies directly**, search for `AmazonEC2FullAccess`, select it, and then choose **Next: Review**.

![Create IAM Group](https://github.com/user-attachments/assets/2267a4e6-fe1e-4cfb-97d1-5e5abd0cb355)

4. Choose **Add permissions**.

![Create IAM Group](https://github.com/user-attachments/assets/d672d146-7f9f-4c60-9d8a-4fefce7f3eff)

5. Repeat the steps for the `S3` group, but attach the `AmazonS3FullAccess` policy.

![Create IAM Group](https://github.com/user-attachments/assets/d6b6c65f-4c34-40f3-998f-8c2e435c022d)

### 4. Add Users to Groups

1. In the navigation pane, choose **User groups** and then select the `EC2` group.
2. Choose the **Users** tab, and then choose **Add users**.
3. Select the checkbox next to `John`, and then choose **Add user**.
4. Repeat the steps for the `S3` group, but add the user `Jenny`.

![Add User to Group](images/add-user-to-group.png)

## Verification

To verify that the users are correctly added to their respective groups and the policies are attached:

1. Go to the **User groups** section in the IAM console and select the `EC2` group. Check the **Users** and **Permissions** tabs to see the user `John` and the attached policy `AmazonEC2FullAccess`.
2. Similarly, check the `S3` group for the user `Jenny` and the attached policy `AmazonS3FullAccess`.

### Images

1. **Creating IAM User**

   ![Create IAM User](images/create-user.png)

2. **Creating IAM Group**

   ![Create IAM Group](images/create-group.png)

3. **Attaching Policy to Group**

   ![Attach Policy](images/attach-policy.png)

4. **Adding User to Group**

   ![Add User to Group](images/add-user-to-group.png)

## Conclusion

By following these steps, you have successfully created IAM users, groups, attached policies to the groups, and added users to the groups. This setup ensures that users have appropriate permissions as per their group policies.

