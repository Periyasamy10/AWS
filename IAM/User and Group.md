# AWS IAM User and Group Management

This guide will walk you through creating IAM users, creating groups, attaching policies to those groups, and adding users to groups using the AWS Management Console.

## Steps

### 1. Create IAM Users

1. Sign in to the AWS Management Console and open the IAM console at https://console.aws.amazon.com/iam/.
2. In the navigation pane, choose **Users** and then choose **Add user**.
3. For **User name**, enter `John`. Select the checkbox next to **AWS Management Console access**, then choose **Next: Permissions**.
4. Repeat the steps for another user, `Jenny`.

![Create IAM User](images/create-user.png)

### 2. Create IAM Groups

1. In the navigation pane, choose **User groups**, and then choose **Create group**.
2. For **User group name**, enter `EC2`. Choose **Create group**.
3. Repeat the steps for another group, `S3`.

![Create IAM Group](images/create-group.png)

### 3. Attach Policies to Groups

1. In the navigation pane, choose **User groups** and then select the `EC2` group.
2. Choose the **Permissions** tab, and then choose **Add permissions**.
3. Choose **Attach policies directly**, search for `AmazonEC2FullAccess`, select it, and then choose **Next: Review**.
4. Choose **Add permissions**.
5. Repeat the steps for the `S3` group, but attach the `AmazonS3FullAccess` policy.

![Attach Policy](images/attach-policy.png)

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

